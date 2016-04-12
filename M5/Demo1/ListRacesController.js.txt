({
	doInit : function(component, event, helper) {
		helper.getRaces(component);
	},
     handleAddToRaces : function(component, event, helper) {
        helper.addToRaces(component, event);   
    }
    
})