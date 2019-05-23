# ![LOGO](logo.png) Firebase Rules **flow**ground Connector

## Description

A generated **flow**ground connector for the Firebase Rules API (version v1).

Generated from: https://api.apis.guru/v2/specs/googleapis.com/firebaserules/v1/swagger.json<br/>
Generated at: 2019-05-23T12:13:23+03:00

## API Description

Creates and manages rules that determine when a Firebase Rules-enabled service should permit a request.


## Authorization

Supported authorization schemes:
- OAuth2

For OAuth 2.0 you need to specify OAuth Client credentials as environment variables in the connector repository:
* `OAUTH_CLIENT_ID` - your OAuth client id
* `OAUTH_CLIENT_SECRET` - your OAuth client secret

## Actions

### Delete a `Release` by resource name.

*Tags:* `projects`

#### Input Parameters
* `name` - _required_ - Resource name for the `Release` to delete.

Format: `projects/{project_id}/releases/{release_id}`
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Get a `Release` by name.

*Tags:* `projects`

#### Input Parameters
* `name` - _required_ - Resource name of the `Release`.

Format: `projects/{project_id}/releases/{release_id}`
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Update a `Release` via PATCH.<br/>
> <br/>
> Only updates to the `ruleset_name` and `test_suite_name` fields will be<br/>
> honored. `Release` rename is not supported. To create a `Release` use the<br/>
> CreateRelease method.

*Tags:* `projects`

#### Input Parameters
* `name` - _required_ - Resource name for the project which owns this `Release`.

Format: `projects/{project_id}`
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### List the `Release` values for a project. This list may optionally be<br/>
> filtered by `Release` name, `Ruleset` name, `TestSuite` name, or any<br/>
> combination thereof.

*Tags:* `projects`

#### Input Parameters
* `filter` - _optional_ - `Release` filter. The list method supports filters with restrictions on the
`Release.name`, `Release.ruleset_name`, and `Release.test_suite_name`.

Example 1: A filter of 'name=prod*' might return `Release`s with names
within 'projects/foo' prefixed with 'prod':

Name                          | Ruleset Name
------------------------------|-------------
projects/foo/releases/prod    | projects/foo/rulesets/uuid1234
projects/foo/releases/prod/v1 | projects/foo/rulesets/uuid1234
projects/foo/releases/prod/v2 | projects/foo/rulesets/uuid8888

Example 2: A filter of `name=prod* ruleset_name=uuid1234` would return only
`Release` instances for 'projects/foo' with names prefixed with 'prod'
referring to the same `Ruleset` name of 'uuid1234':

Name                          | Ruleset Name
------------------------------|-------------
projects/foo/releases/prod    | projects/foo/rulesets/1234
projects/foo/releases/prod/v1 | projects/foo/rulesets/1234

In the examples, the filter parameters refer to the search filters are
relative to the project. Fully qualified prefixed may also be used. e.g.
`test_suite_name=projects/foo/testsuites/uuid1`
* `name` - _required_ - Resource name for the project.

Format: `projects/{project_id}`
* `pageSize` - _optional_ - Page size to load. Maximum of 100. Defaults to 10.
Note: `page_size` is just a hint and the service may choose to load fewer
than `page_size` results due to the size of the output. To traverse all of
the releases, the caller should iterate until the `page_token` on the
response is empty.
* `pageToken` - _optional_ - Next page token for the next batch of `Release` instances.
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Create a `Release`.<br/>
> <br/>
> Release names should reflect the developer's deployment practices. For<br/>
> example, the release name may include the environment name, application<br/>
> name, application version, or any other name meaningful to the developer.<br/>
> Once a `Release` refers to a `Ruleset`, the rules can be enforced by<br/>
> Firebase Rules-enabled services.<br/>
> <br/>
> More than one `Release` may be 'live' concurrently. Consider the following<br/>
> three `Release` names for `projects/foo` and the `Ruleset` to which they<br/>
> refer.<br/>
> <br/>
> Release Name                    | Ruleset Name<br/>
> --------------------------------|-------------<br/>
> projects/foo/releases/prod      | projects/foo/rulesets/uuid123<br/>
> projects/foo/releases/prod/beta | projects/foo/rulesets/uuid123<br/>
> projects/foo/releases/prod/v23  | projects/foo/rulesets/uuid456<br/>
> <br/>
> The table reflects the `Ruleset` rollout in progress. The `prod` and<br/>
> `prod/beta` releases refer to the same `Ruleset`. However, `prod/v23`<br/>
> refers to a new `Ruleset`. The `Ruleset` reference for a `Release` may be<br/>
> updated using the UpdateRelease method.

*Tags:* `projects`

#### Input Parameters
* `name` - _required_ - Resource name for the project which owns this `Release`.

Format: `projects/{project_id}`
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### List `Ruleset` metadata only and optionally filter the results by `Ruleset`<br/>
> name.<br/>
> <br/>
> The full `Source` contents of a `Ruleset` may be retrieved with<br/>
> GetRuleset.

*Tags:* `projects`

#### Input Parameters
* `filter` - _optional_ - `Ruleset` filter. The list method supports filters with restrictions on
`Ruleset.name`.

Filters on `Ruleset.create_time` should use the `date` function which
parses strings that conform to the RFC 3339 date/time specifications.

Example: `create_time > date("2017-01-01") AND name=UUID-*`
* `name` - _required_ - Resource name for the project.

Format: `projects/{project_id}`
* `pageSize` - _optional_ - Page size to load. Maximum of 100. Defaults to 10.
Note: `page_size` is just a hint and the service may choose to load less
than `page_size` due to the size of the output. To traverse all of the
releases, caller should iterate until the `page_token` is empty.
* `pageToken` - _optional_ - Next page token for loading the next batch of `Ruleset` instances.
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Create a `Ruleset` from `Source`.<br/>
> <br/>
> The `Ruleset` is given a unique generated name which is returned to the<br/>
> caller. `Source` containing syntactic or semantics errors will result in an<br/>
> error response indicating the first error encountered. For a detailed view<br/>
> of `Source` issues, use TestRuleset.

*Tags:* `projects`

#### Input Parameters
* `name` - _required_ - Resource name for Project which owns this `Ruleset`.

Format: `projects/{project_id}`
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Get the `Release` executable to use when enforcing rules.

*Tags:* `projects`

#### Input Parameters
* `executableVersion` - _optional_ - The requested runtime executable version.
Defaults to FIREBASE_RULES_EXECUTABLE_V1.
    Possible values: RELEASE_EXECUTABLE_VERSION_UNSPECIFIED, FIREBASE_RULES_EXECUTABLE_V1, FIREBASE_RULES_EXECUTABLE_V2.
* `name` - _required_ - Resource name of the `Release`.

Format: `projects/{project_id}/releases/{release_id}`
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Test `Source` for syntactic and semantic correctness. Issues present, if<br/>
> any, will be returned to the caller with a description, severity, and<br/>
> source location.<br/>
> <br/>
> The test method may be executed with `Source` or a `Ruleset` name.<br/>
> Passing `Source` is useful for unit testing new rules. Passing a `Ruleset`<br/>
> name is useful for regression testing an existing rule.<br/>
> <br/>
> The following is an example of `Source` that permits users to upload images<br/>
> to a bucket bearing their user id and matching the correct metadata:<br/>
> <br/>
> _*Example*_<br/>
> <br/>
>     // Users are allowed to subscribe and unsubscribe to the blog.<br/>
>     service firebase.storage {<br/>
>       match /users/{userId}/images/{imageName} {<br/>
>           allow write: if userId == request.auth.uid<br/>
>               && (imageName.matches('*.png$')<br/>
>               || imageName.matches('*.jpg$'))<br/>
>               && resource.mimeType.matches('^image/')<br/>
>       }<br/>
>     }

*Tags:* `projects`

#### Input Parameters
* `name` - _required_ - Tests may either provide `source` or a `Ruleset` resource name.

For tests against `source`, the resource name must refer to the project:
Format: `projects/{project_id}`

For tests against a `Ruleset`, this must be the `Ruleset` resource name:
Format: `projects/{project_id}/rulesets/{ruleset_id}`
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

## License

**flow**ground :- Telekom iPaaS / googleapis-com-firebaserules-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
