# Power-Automate-Dataverse-Utilities
Group of Utility Child Flows that can be used to enhance your Power Automate Cloud Flows

To Install, grab the solution ZIP file from the <a href=https://github.com/InformDyn365/Power-Automate-Dataverse-Utilities/releases>releases page</a> and import to your environment. You will need to update the (2) connection references for Dataverse and Office 365 Outlook

<strong>PAUTIL.PA.Child.GetGuidByName</strong> - Pass in a table name, column name, and column value to search the entity for that specific row, then return the GUID for that row. E.g.: Search the Teams table for a specific team by Name, then return the GUID for that Team.

PAUTIL.PA.ChildFlow.ErrorHandler - Pass in the workflow() and Email Address to notify from a flow to send out an email that an error has occurred. To use, create 2 Scope actions (e.g. Try and Catch). Place your main set of actions inside the <strong>Try</strong> scope. Then in the <strong>Configure run after</strong> of the <strong>Catch</strong> scope, check the boxes for it to run when the <strong>Try</strong> scope <strong>has failed</strong> or <strong>has timed out</strong>. Open the PAUTIL.PA.Child.GetGuidByName cloud flow to see an example.

PAUTIL.PA.ChildFlow.GetRowURL - Pass in the BODY of a Dataverse 'Get Row by ID' action. Flow will parse the returned data to get the URL to the specific row. This can then be included in Emails or written directly to the row in a custom field.

PAUTIL.PA.ChildFlow.GetTeamMemberEmails - Pass in a Team GUID. Flow will loop through members of the team and return a semi-colon delimited list of email addresses for each team member from their user record. List can be used in an outlook email action.

PAUTIL.PA.ChildFlow.GetTeamMembersActivityPartyList - Pass in a GUID for a Team. Flow will get the members of that team and return a string of Activity Party entries to be used in a Dataverse Email Activity. Be sure and edit the variable strParticipationTypeMask value if you want something other than TO (2). CC = 3 and BCC = 4

