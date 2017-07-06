[![](https://scdn.rapidapi.com/RapidAPI_banner.png)](https://rapidapi.com/package/OnFleet/functions?utm_source=RapidAPIGitHub_OnFleetFunctions&utm_medium=button&utm_content=RapidAPI_GitHub)

# OnFleet Package
The Onfleet API is a RESTful web service for developers and integrations to programmatically interact with Onfleet’s data and real-time delivery management and analytics functionality.
* Domain: [OnFleet](http://onfleet.com)
* Credentials: apiKey

## How to get credentials: 

0. Please contact OnFleet directly for apiKey

 ## Webhook credentials
 
 Please use SDK to test this feature.
 
 0. Go to [RapidAPI](http://rapidapi.com)
 1. Log in or create an account
 2. Go to [My apps](https://dashboard.rapidapi.com/projects)
 3. Add new project with projectName to get your project Key
 
 | Field      | Type       | Description
 |------------|------------|----------
 | projectName     | credentials| Your RapidAPI project name
 | projectKey | credentials     | Your RapidAPI project key

## Custom datatypes: 
 |Datatype|Description|Example
 |--------|-----------|----------
 |Datepicker|String which includes date and time|```2016-05-28 00:00:00```
 |Map|String which includes latitude and longitude coma separated|```50.37, 26.56```
 |List|Simple array|```["123", "sample"]``` 
 |Select|String with predefined values|```sample```
 |Array|Array of objects|```[{"Second name":"123","Age":"12","Photo":"sdf","Draft":"sdfsdf"},{"name":"adi","Second name":"bla","Age":"4","Photo":"asfserwe","Draft":"sdfsdf"}] ```
 

## OnFleet.testAuth
Check that your API key is valid.

| Field | Type       | Description
|-------|------------|----------
| apiKey| credentials| Api key obtained from OnFleet

## OnFleet.getOrganizationDetails
Retrieve your own organization's details.

| Field | Type       | Description
|-------|------------|----------
| apiKey| credentials| Api key obtained from OnFleet

## OnFleet.getDelegateeDetails
Retrieve the details of an organization with which you are connected.

| Field         | Type       | Description
|---------------|------------|----------
| apiKey        | credentials| Api key obtained from OnFleet
| organizationId| String     | Id of the organization

## OnFleet.createAdministrator
Creates a new administrator in your organization. An email will be sent for this administrator to confirm and configure their account.

| Field     | Type       | Description
|-----------|------------|----------
| apiKey    | credentials| Api key obtained from OnFleet
| name      | String     | The administrator’s complete name.
| email     | String     | The administrator’s email address.
| phone     | String     | The administrator's phone number.
| isReadOnly| String     | Whether this administrator can perform write operations.

## OnFleet.listAdministrators
Lists administrators

| Field | Type       | Description
|-------|------------|----------
| apiKey| credentials| Api key obtained from OnFleet

## OnFleet.updateAdministrator
Updates an administrator in your organization.

| Field          | Type       | Description
|----------------|------------|----------
| apiKey         | credentials| Api key obtained from OnFleet
| administratorId| String     | The administrator’s id
| name           | String     | The administrator’s complete name.
| email          | String     | The administrator’s email address.
| phone          | String     | The administrator's phone number.
| isReadOnly     | String     | Whether this administrator can perform write operations.

## OnFleet.deleteAdministrator
Deletes an administrator in your organization.

| Field          | Type       | Description
|----------------|------------|----------
| apiKey         | credentials| Api key obtained from OnFleet
| administratorId| String     | The administrator’s id

## OnFleet.createWorker
Creating a new worker generates a temporary password which is sent to the worker’s phone by SMS along with download details for the worker iOS and Android mobile apps.

| Field   | Type       | Description
|---------|------------|----------
| apiKey  | credentials| Api key obtained from OnFleet
| name    | String     | The worker’s complete name.
| phone   | String     | A valid phone number as per the worker’s organization’s country.
| teams   | List       | One or more team IDs of which the worker is a member.
| vehicle | JSON       | The worker’s vehicle; providing no vehicle details is equivalent to the worker being on foot.
| capacity| Number     | The maximum number of units this worker can carry, for route optimization purposes.

## OnFleet.listWorkers
List all available workers

| Field | Type       | Description
|-------|------------|----------
| apiKey| credentials| Api key obtained from OnFleet
| teams | List       | An array of the team IDs that workers must be part of.
| filter| List       |  An array of fields to return, if all are not desired. For example, name, location.
| states| List       |  An array of worker states, where 0 is off-duty, 1 is idle (on-duty, no active task) and 2 is active (on-duty, active task).

## OnFleet.getWorkersByLocation
List all available workers by coordinates

| Field      | Type       | Description
|------------|------------|----------
| apiKey     | credentials| Api key obtained from OnFleet
| coordinates| Map        | Longitude and latitude coma-separated
| radius     | Number     | The length in meters of the radius of the spherical area in which to look for workers. Defaults to 1000 if missing. Maximum value is 10000.

## OnFleet.getSingleWorker
Get single worker by Id

| Field   | Type       | Description
|---------|------------|----------
| apiKey  | credentials| Api key obtained from OnFleet
| workerId| String     | Id of the worker
| filter  | List       |  An array of fields to return, if all are not desired. For example, name, location.

## OnFleet.updateWorker
Update existing worker

| Field   | Type       | Description
|---------|------------|----------
| apiKey  | credentials| Api key obtained from OnFleet
| workerId| String     | Id of the worker
| name    | String     | The worker’s complete name.
| teams   | List       | One or more team IDs of which the worker is a member.
| vehicle | JSON       | The worker’s vehicle; providing no vehicle details is equivalent to the worker being on foot.
| capacity| Number     | The maximum number of units this worker can carry, for route optimization purposes.

## OnFleet.deleteWorker
Delete single worker by Id

| Field   | Type       | Description
|---------|------------|----------
| apiKey  | credentials| Api key obtained from OnFleet
| workerId| String     | Id of the worker

## OnFleet.listHubs
A hub is a depot for a team: the location from where all deliveries start for the team's workers, for the purposes of route optimization only; teams can have zero or one hubs. To create hubs, head over to the dashboard.

| Field | Type       | Description
|-------|------------|----------
| apiKey| credentials| Api key obtained from OnFleet

## OnFleet.createTeam
Teams are named entities that bring together administrators and workers belonging to the same organization. Teams have hubs from where its workers may start and end their shifts.

| Field   | Type       | Description
|---------|------------|----------
| apiKey  | credentials| Api key obtained from OnFleet
| name    | String     | A unique name for the team.
| workers | List       | An array of worker IDs.
| managers| List       | An array of managing administrator IDs.
| hub     | String     | The ID of the team's hub.

## OnFleet.updateTeam
Update existing team

| Field   | Type       | Description
|---------|------------|----------
| apiKey  | credentials| Api key obtained from OnFleet
| teamId  | String     | A unique id of the team
| name    | String     | A unique name for the team.
| workers | List       | An array of worker IDs.
| managers| List       | An array of managing administrator IDs.
| hub     | String     | The ID of the team's hub.

## OnFleet.listTeams
List all available teams.

| Field | Type       | Description
|-------|------------|----------
| apiKey| credentials| Api key obtained from OnFleet

## OnFleet.getSingleTeam
Get single team information

| Field | Type       | Description
|-------|------------|----------
| apiKey| credentials| Api key obtained from OnFleet
| teamId| String     | Single team id

## OnFleet.deleteTeam
Delete single team

| Field | Type       | Description
|-------|------------|----------
| apiKey| credentials| Api key obtained from OnFleet
| teamId| String     | Single team id

## OnFleet.createDestination
Destinations represent the location details for tasks, including exact coordinate and address information.

| Field            | Type       | Description
|------------------|------------|----------
| apiKey           | credentials| Api key obtained from OnFleet
| addressName      | String     | A name associated with this address.
| addressNumber    | String     | The number component of this address, it may also contain letters.
| addressStreet    | String     | The name of the street.
| addressApartment | String     | The suite or apartment number, or any additional relevant information.
| addressCity      | String     | The name of the municipality.
| addressState     | String     | The name of the state, province or jurisdiction.
| addressPostalCode| String     | The postal or zip code.
| addressCountry   | String     | The name of the country.
| coordinates      | Map        | The longitude, latitude coma-separated. If missing, the API will geocode based on the address details provided. Note that geocoding may slightly modify the format of the address properties. 

## OnFleet.createDestinationFromRaw
Destinations represent the location details for tasks, including exact coordinate and address information.

| Field   | Type       | Description
|---------|------------|----------
| apiKey  | credentials| Api key obtained from OnFleet
| unparsed| String     | A complete address specified in a single, unparsed string where the various elements are separated by commas.

## OnFleet.getSingleDestination
Get single destionation by Id

| Field        | Type       | Description
|--------------|------------|----------
| apiKey       | credentials| Api key obtained from OnFleet
| destinationId| String     | Id of the destination

## OnFleet.createRecipient
A recipient is an organization’s customer and a target for a task, that is, whom the task is being delivered to.

| Field                    | Type       | Description
|--------------------------|------------|----------
| apiKey                   | credentials| Api key obtained from OnFleet
| name                     | String     | The recipient’s complete name.
| phone                    | String     | A unique, valid phone number as per the recipient’s organization’s country.
| notes                    | String     | Notes for this recipient: these are global notes that should not be task- or destination-specific.
| skipSMSNotifications     | Boolean    | Whether this recipient has requested to not receive SMS notifications. Defaults to false if not provided.
| skipPhoneNumberValidation| Boolean    | Whether to skip validation of this recipient's phone number. An E.164-like number is still required (must start with +), however the API will not enforce any country-specific validation rules.

## OnFleet.updateRecipient
Update existing recipient.

| Field                    | Type       | Description
|--------------------------|------------|----------
| apiKey                   | credentials| Api key obtained from OnFleet
| recipientId              | String     | The recipient’s id
| name                     | String     | The recipient’s complete name.
| phone                    | String     | A unique, valid phone number as per the recipient’s organization’s country.
| notes                    | String     | Notes for this recipient: these are global notes that should not be task- or destination-specific.
| skipSMSNotifications     | Boolean    | Whether this recipient has requested to not receive SMS notifications. Defaults to false if not provided.
| skipPhoneNumberValidation| Boolean    | Whether to skip validation of this recipient's phone number. An E.164-like number is still required (must start with +), however the API will not enforce any country-specific validation rules.

## OnFleet.findRecipientByPhone
Search for recipient by phone

| Field | Type       | Description
|-------|------------|----------
| apiKey| credentials| Api key obtained from OnFleet
| phone | String     | A unique, valid phone number as per the recipient’s organization’s country.

## OnFleet.findRecipientByName
Search for recipient by name

| Field | Type       | Description
|-------|------------|----------
| apiKey| credentials| Api key obtained from OnFleet
| name  | String     | The recipient’s name.

## OnFleet.getSingleRecipient
Get single recipient

| Field      | Type       | Description
|------------|------------|----------
| apiKey     | credentials| Api key obtained from OnFleet
| recipientId| String     | The recipient’s id.

## OnFleet.createTask
Create new task

| Field         | Type       | Description
|---------------|------------|----------
| apiKey        | credentials| Api key obtained from OnFleet
| merchant      | String     | The ID of the organization that will be displayed to the recipient of the task. Defaults to the creating organization. If you perform deliveries on behalf of a connected organization and want to display their name, logo, and branded notifications, provide their organization ID.
| executor      | String     | The ID of the organization that will be responsible for fulfilling the task. Defaults to the creating organization. If you delegate your deliveries to a third party, provide their organization ID.
| destinationId | String     | The ID of the task's destination
| recipientsIds | List       | An array containing zero or one IDs of the task's recipients
| completeAfter | DatePicker | A date Y-m-d H:m :s for the earliest time the task should be completed.
| completeBefore| DatePicker | A date Y-m-d H:m :s for the latest time the task should be completed.
| pickupTask    | Boolean    | Whether the task is a pickup task.
| dependencies  | List       | One or more IDs of tasks which must be completed prior to this task.
| notes         | String     | Notes for the task.
| autoAssign    | JSON       | The automatic assignment options for the newly created task. You may not provide a container if using automatic assignment.
| container     | JSON       | The container to which to append this task. Defaults to the creator organization container.
| quantity      | Number     | The number of units to be dropped off while completing this task, for route optimization purposes.
| serviceTime   | Number     | The number of minutes to be spent by the worker on arrival at this task's destination, for route optimization purposes.

## OnFleet.listTasks
Returns a paginated collection of all tasks in your organization.

| Field | Type       | Description
|-------|------------|----------
| apiKey| credentials| Api key obtained from OnFleet
| from  | DatePicker | The starting time of the range.
| to    | DatePicker | If missing, defaults to the current time. The ending time of the range. Tasks created or completed before this time will be included.
| lastId| String     | Used to walk the paginated response, if there is one. Tasks created after this ID will be returned.

## OnFleet.getSingleTask
Returns a single task by its id

| Field | Type       | Description
|-------|------------|----------
| apiKey| credentials| Api key obtained from OnFleet
| taskId| String     | Id of the task

## OnFleet.getSingleTaskByShortId
Returns a single task by its short id

| Field      | Type       | Description
|------------|------------|----------
| apiKey     | credentials| Api key obtained from OnFleet
| taskShortId| String     | Short id of the task

## OnFleet.updateTask
Note that, for active tasks, only notes can be updated, while completed tasks cannot be updated in any way. 

| Field | Type       | Description
|-------|------------|----------
| apiKey| credentials| Api key obtained from OnFleet
| taskId| String     | Id of the task
| notes | String     | Task notes

## OnFleet.completeTask
Note that, for active tasks, only notes can be updated, while completed tasks cannot be updated in any way. 

| Field  | Type       | Description
|--------|------------|----------
| apiKey | credentials| Api key obtained from OnFleet
| taskId | String     | Id of the task
| success| Boolean    | Whether the task's completion was successful.
| notes  | String     | Any completion notes for the task.

## OnFleet.cloneTask
The property sourceTaskId can be used to keep track of the source task from which the task was cloned.

| Field | Type       | Description
|-------|------------|----------
| apiKey| credentials| Api key obtained from OnFleet
| taskId| String     | Id of the task

## OnFleet.deleteTask
Active or completed tasks cannot be deleted.

| Field | Type       | Description
|-------|------------|----------
| apiKey| credentials| Api key obtained from OnFleet
| taskId| String     | Id of the task

## OnFleet.insertTasksAtIndex
You may insert one or more tasks at a given index by providing the index as the first element in the array, followed by the task IDs.

| Field        | Type       | Description
|--------------|------------|----------
| apiKey       | credentials| Api key obtained from OnFleet
| containerType| Select     | Type of the container to insert
| entityId     | String     | Id of the container of provided type
| index        | String     |  To append to the end, use -1 as your index. To prepend, use 0. For example, if you want to insert two tasks at position 3 for a given worker, such that all currently assigned tasks at index >= 3 are shifted forward
| tasks        | List       | Array of tasks to insert

## OnFleet.updateTasks
You may also fully replace a container's tasks by omitting the index and providing a complete list of task IDs.

| Field               | Type       | Description
|---------------------|------------|----------
| apiKey              | credentials| Api key obtained from OnFleet
| containerType       | Select     | Type of the container to insert
| entityId            | String     | Id of the container of provided type
| tasks               | List       | Array of tasks to insert
| considerDependencies| Boolean    | Whether to include the target task's dependency family (parent and child tasks) in the resulting assignment operation.

## OnFleet.createWebhook
Webhooks make it possible for your application to be notified of important system events, as soon as these take place within Onfleet.

 You can use our service as url: 
   ```
   https://webhooks.rapidapi.com/api/message/OnFleet/webhookEvent/{projectName}/{projectKey} * see credentials description above
   ```

| Field    | Type       | Description
|----------|------------|----------
| apiKey   | credentials| Api key obtained from OnFleet
| url      | String     | The URL that Onfleet should issue a request against as soon as the trigger condition is met.
| trigger  | Number     | The number corresponding to the trigger condition on which the webhook should fire: http://docs.onfleet.com/docs/webhooks
| threshold| Number     | For trigger 1, the time threshold in seconds; for trigger 2, the distance threshold in meters.

## OnFleet.listWebhooks
Get all webhooks

| Field | Type       | Description
|-------|------------|----------
| apiKey| credentials| Api key obtained from OnFleet

## OnFleet.deleteWebhook
Delete single webhook

| Field    | Type       | Description
|----------|------------|----------
| apiKey   | credentials| Api key obtained from OnFleet
| webhookId| String     | Id of the webhook

