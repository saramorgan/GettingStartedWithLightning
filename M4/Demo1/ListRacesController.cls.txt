public with sharing class ListRacesController {

    @AuraEnabled
    public static List<Race__c> getRacesDB() {
       
        return [SELECT Id, Name, DateTime__c, Location__c, 
                Attended__c, Type__c, Results__c FROM Race__c];
    }
   
}