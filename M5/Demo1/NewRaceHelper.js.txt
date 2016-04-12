({
	loadOptions : function(component,event, helper) {
        
		var types = [
            {class: "optionClass", label: "5K", value: "5K"},
            {class: "optionClass", label: "10K", value: "10K"},
            {class: "optionClass", label: "Half-Marathon", value: "Half-Marathon"}
        ];
        component.find("Type").set("v.options", types);
        
	},
    createNewRace : function(component) {    
        
        var action = component.get("c.newRaceDB");
        action.setParams({ "race" : component.get("v.newRace") });
        action.setCallback(this, function(response) {
            var state = response.getState();
            if (component.isValid() && state === "SUCCESS") {
                console.log("Race successfully saved");
				// Fire off application event after successful save
				var appEvent = $A.get("e.c:addToRaceList");
                appEvent.setParams({ "race" : response.getReturnValue() });
                appEvent.fire(); 
            } else if (state === "ERROR") {
                var errors = response.getError();
                if (errors) {
                    if (errors[0] && errors[0].message) {
                        console.log("Error message: " + errors[0].message);
                    }
                } else {
                    console.log("Unknown error");
                }
            } else {
                console.log("Action State returned was: " + state);
            }

        });
        $A.enqueueAction(action);

    }
    
})