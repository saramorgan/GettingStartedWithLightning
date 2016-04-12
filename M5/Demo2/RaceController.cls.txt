public with sharing class RaceController {

	@AuraEnabled
    public static Race__c updateRaceDB(Race__c race) {
  
        update race;
        return race;
    }
}