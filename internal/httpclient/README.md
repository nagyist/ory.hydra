# Go API client for openapi

Documentation for all of Ory Hydra's APIs.


## Overview
This API client was generated by the [OpenAPI Generator](https://openapi-generator.tech) project.  By using the [OpenAPI-spec](https://www.openapis.org/) from a remote server, you can easily generate an API client.

- API version: 
- Package version: 1.0.0
- Build package: org.openapitools.codegen.languages.GoClientCodegen

## Installation

Install the following dependencies:

```sh
go get github.com/stretchr/testify/assert
go get golang.org/x/oauth2
go get golang.org/x/net/context
```

Put the package under your project folder and add the following in import:

```go
import openapi "github.com/ory/hydra-client-go/v2"
```

To use a proxy, set the environment variable `HTTP_PROXY`:

```go
os.Setenv("HTTP_PROXY", "http://proxy_name:proxy_port")
```

## Configuration of Server URL

Default configuration comes with `Servers` field that contains server objects as defined in the OpenAPI specification.

### Select Server Configuration

For using other server than the one defined on index 0 set context value `openapi.ContextServerIndex` of type `int`.

```go
ctx := context.WithValue(context.Background(), openapi.ContextServerIndex, 1)
```

### Templated Server URL

Templated server URL is formatted using default variables from configuration or from context value `openapi.ContextServerVariables` of type `map[string]string`.

```go
ctx := context.WithValue(context.Background(), openapi.ContextServerVariables, map[string]string{
	"basePath": "v2",
})
```

Note, enum values are always validated and all unused variables are silently ignored.

### URLs Configuration per Operation

Each operation can use different server URL defined using `OperationServers` map in the `Configuration`.
An operation is uniquely identified by `"{classname}Service.{nickname}"` string.
Similar rules for overriding default operation server index and variables applies by using `openapi.ContextOperationServerIndices` and `openapi.ContextOperationServerVariables` context maps.

```go
ctx := context.WithValue(context.Background(), openapi.ContextOperationServerIndices, map[string]int{
	"{classname}Service.{nickname}": 2,
})
ctx = context.WithValue(context.Background(), openapi.ContextOperationServerVariables, map[string]map[string]string{
	"{classname}Service.{nickname}": {
		"port": "8443",
	},
})
```

## Documentation for API Endpoints

All URIs are relative to *http://localhost*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*JwkAPI* | [**CreateJsonWebKeySet**](docs/JwkAPI.md#createjsonwebkeyset) | **Post** /admin/keys/{set} | Create JSON Web Key
*JwkAPI* | [**DeleteJsonWebKey**](docs/JwkAPI.md#deletejsonwebkey) | **Delete** /admin/keys/{set}/{kid} | Delete JSON Web Key
*JwkAPI* | [**DeleteJsonWebKeySet**](docs/JwkAPI.md#deletejsonwebkeyset) | **Delete** /admin/keys/{set} | Delete JSON Web Key Set
*JwkAPI* | [**GetJsonWebKey**](docs/JwkAPI.md#getjsonwebkey) | **Get** /admin/keys/{set}/{kid} | Get JSON Web Key
*JwkAPI* | [**GetJsonWebKeySet**](docs/JwkAPI.md#getjsonwebkeyset) | **Get** /admin/keys/{set} | Retrieve a JSON Web Key Set
*JwkAPI* | [**SetJsonWebKey**](docs/JwkAPI.md#setjsonwebkey) | **Put** /admin/keys/{set}/{kid} | Set JSON Web Key
*JwkAPI* | [**SetJsonWebKeySet**](docs/JwkAPI.md#setjsonwebkeyset) | **Put** /admin/keys/{set} | Update a JSON Web Key Set
*MetadataAPI* | [**GetVersion**](docs/MetadataAPI.md#getversion) | **Get** /version | Return Running Software Version.
*MetadataAPI* | [**IsAlive**](docs/MetadataAPI.md#isalive) | **Get** /health/alive | Check HTTP Server Status
*MetadataAPI* | [**IsReady**](docs/MetadataAPI.md#isready) | **Get** /health/ready | Check HTTP Server and Database Status
*OAuth2API* | [**AcceptOAuth2ConsentRequest**](docs/OAuth2API.md#acceptoauth2consentrequest) | **Put** /admin/oauth2/auth/requests/consent/accept | Accept OAuth 2.0 Consent Request
*OAuth2API* | [**AcceptOAuth2LoginRequest**](docs/OAuth2API.md#acceptoauth2loginrequest) | **Put** /admin/oauth2/auth/requests/login/accept | Accept OAuth 2.0 Login Request
*OAuth2API* | [**AcceptOAuth2LogoutRequest**](docs/OAuth2API.md#acceptoauth2logoutrequest) | **Put** /admin/oauth2/auth/requests/logout/accept | Accept OAuth 2.0 Session Logout Request
*OAuth2API* | [**AcceptUserCodeRequest**](docs/OAuth2API.md#acceptusercoderequest) | **Put** /admin/oauth2/auth/requests/device/accept | Accepts a device grant user_code request
*OAuth2API* | [**CreateOAuth2Client**](docs/OAuth2API.md#createoauth2client) | **Post** /admin/clients | Create OAuth 2.0 Client
*OAuth2API* | [**DeleteOAuth2Client**](docs/OAuth2API.md#deleteoauth2client) | **Delete** /admin/clients/{id} | Delete OAuth 2.0 Client
*OAuth2API* | [**DeleteOAuth2Token**](docs/OAuth2API.md#deleteoauth2token) | **Delete** /admin/oauth2/tokens | Delete OAuth 2.0 Access Tokens from specific OAuth 2.0 Client
*OAuth2API* | [**DeleteTrustedOAuth2JwtGrantIssuer**](docs/OAuth2API.md#deletetrustedoauth2jwtgrantissuer) | **Delete** /admin/trust/grants/jwt-bearer/issuers/{id} | Delete Trusted OAuth2 JWT Bearer Grant Type Issuer
*OAuth2API* | [**GetOAuth2Client**](docs/OAuth2API.md#getoauth2client) | **Get** /admin/clients/{id} | Get an OAuth 2.0 Client
*OAuth2API* | [**GetOAuth2ConsentRequest**](docs/OAuth2API.md#getoauth2consentrequest) | **Get** /admin/oauth2/auth/requests/consent | Get OAuth 2.0 Consent Request
*OAuth2API* | [**GetOAuth2LoginRequest**](docs/OAuth2API.md#getoauth2loginrequest) | **Get** /admin/oauth2/auth/requests/login | Get OAuth 2.0 Login Request
*OAuth2API* | [**GetOAuth2LogoutRequest**](docs/OAuth2API.md#getoauth2logoutrequest) | **Get** /admin/oauth2/auth/requests/logout | Get OAuth 2.0 Session Logout Request
*OAuth2API* | [**GetTrustedOAuth2JwtGrantIssuer**](docs/OAuth2API.md#gettrustedoauth2jwtgrantissuer) | **Get** /admin/trust/grants/jwt-bearer/issuers/{id} | Get Trusted OAuth2 JWT Bearer Grant Type Issuer
*OAuth2API* | [**IntrospectOAuth2Token**](docs/OAuth2API.md#introspectoauth2token) | **Post** /admin/oauth2/introspect | Introspect OAuth2 Access and Refresh Tokens
*OAuth2API* | [**ListOAuth2Clients**](docs/OAuth2API.md#listoauth2clients) | **Get** /admin/clients | List OAuth 2.0 Clients
*OAuth2API* | [**ListOAuth2ConsentSessions**](docs/OAuth2API.md#listoauth2consentsessions) | **Get** /admin/oauth2/auth/sessions/consent | List OAuth 2.0 Consent Sessions of a Subject
*OAuth2API* | [**ListTrustedOAuth2JwtGrantIssuers**](docs/OAuth2API.md#listtrustedoauth2jwtgrantissuers) | **Get** /admin/trust/grants/jwt-bearer/issuers | List Trusted OAuth2 JWT Bearer Grant Type Issuers
*OAuth2API* | [**OAuth2Authorize**](docs/OAuth2API.md#oauth2authorize) | **Get** /oauth2/auth | OAuth 2.0 Authorize Endpoint
*OAuth2API* | [**OAuth2DeviceFlow**](docs/OAuth2API.md#oauth2deviceflow) | **Post** /oauth2/device/auth | The OAuth 2.0 Device Authorize Endpoint
*OAuth2API* | [**Oauth2TokenExchange**](docs/OAuth2API.md#oauth2tokenexchange) | **Post** /oauth2/token | The OAuth 2.0 Token Endpoint
*OAuth2API* | [**PatchOAuth2Client**](docs/OAuth2API.md#patchoauth2client) | **Patch** /admin/clients/{id} | Patch OAuth 2.0 Client
*OAuth2API* | [**PerformOAuth2DeviceVerificationFlow**](docs/OAuth2API.md#performoauth2deviceverificationflow) | **Get** /oauth2/device/verify | OAuth 2.0 Device Verification Endpoint
*OAuth2API* | [**RejectOAuth2ConsentRequest**](docs/OAuth2API.md#rejectoauth2consentrequest) | **Put** /admin/oauth2/auth/requests/consent/reject | Reject OAuth 2.0 Consent Request
*OAuth2API* | [**RejectOAuth2LoginRequest**](docs/OAuth2API.md#rejectoauth2loginrequest) | **Put** /admin/oauth2/auth/requests/login/reject | Reject OAuth 2.0 Login Request
*OAuth2API* | [**RejectOAuth2LogoutRequest**](docs/OAuth2API.md#rejectoauth2logoutrequest) | **Put** /admin/oauth2/auth/requests/logout/reject | Reject OAuth 2.0 Session Logout Request
*OAuth2API* | [**RevokeOAuth2ConsentSessions**](docs/OAuth2API.md#revokeoauth2consentsessions) | **Delete** /admin/oauth2/auth/sessions/consent | Revoke OAuth 2.0 Consent Sessions of a Subject
*OAuth2API* | [**RevokeOAuth2LoginSessions**](docs/OAuth2API.md#revokeoauth2loginsessions) | **Delete** /admin/oauth2/auth/sessions/login | Revokes OAuth 2.0 Login Sessions by either a Subject or a SessionID
*OAuth2API* | [**RevokeOAuth2Token**](docs/OAuth2API.md#revokeoauth2token) | **Post** /oauth2/revoke | Revoke OAuth 2.0 Access or Refresh Token
*OAuth2API* | [**SetOAuth2Client**](docs/OAuth2API.md#setoauth2client) | **Put** /admin/clients/{id} | Set OAuth 2.0 Client
*OAuth2API* | [**SetOAuth2ClientLifespans**](docs/OAuth2API.md#setoauth2clientlifespans) | **Put** /admin/clients/{id}/lifespans | Set OAuth2 Client Token Lifespans
*OAuth2API* | [**TrustOAuth2JwtGrantIssuer**](docs/OAuth2API.md#trustoauth2jwtgrantissuer) | **Post** /admin/trust/grants/jwt-bearer/issuers | Trust OAuth2 JWT Bearer Grant Type Issuer
*OidcAPI* | [**CreateOidcDynamicClient**](docs/OidcAPI.md#createoidcdynamicclient) | **Post** /oauth2/register | Register OAuth2 Client using OpenID Dynamic Client Registration
*OidcAPI* | [**CreateVerifiableCredential**](docs/OidcAPI.md#createverifiablecredential) | **Post** /credentials | Issues a Verifiable Credential
*OidcAPI* | [**DeleteOidcDynamicClient**](docs/OidcAPI.md#deleteoidcdynamicclient) | **Delete** /oauth2/register/{id} | Delete OAuth 2.0 Client using the OpenID Dynamic Client Registration Management Protocol
*OidcAPI* | [**DiscoverOidcConfiguration**](docs/OidcAPI.md#discoveroidcconfiguration) | **Get** /.well-known/openid-configuration | OpenID Connect Discovery
*OidcAPI* | [**GetOidcDynamicClient**](docs/OidcAPI.md#getoidcdynamicclient) | **Get** /oauth2/register/{id} | Get OAuth2 Client using OpenID Dynamic Client Registration
*OidcAPI* | [**GetOidcUserInfo**](docs/OidcAPI.md#getoidcuserinfo) | **Get** /userinfo | OpenID Connect Userinfo
*OidcAPI* | [**RevokeOidcSession**](docs/OidcAPI.md#revokeoidcsession) | **Get** /oauth2/sessions/logout | OpenID Connect Front- and Back-channel Enabled Logout
*OidcAPI* | [**SetOidcDynamicClient**](docs/OidcAPI.md#setoidcdynamicclient) | **Put** /oauth2/register/{id} | Set OAuth2 Client using OpenID Dynamic Client Registration
*WellknownAPI* | [**DiscoverJsonWebKeys**](docs/WellknownAPI.md#discoverjsonwebkeys) | **Get** /.well-known/jwks.json | Discover Well-Known JSON Web Keys


## Documentation For Models

 - [AcceptDeviceUserCodeRequest](docs/AcceptDeviceUserCodeRequest.md)
 - [AcceptOAuth2ConsentRequest](docs/AcceptOAuth2ConsentRequest.md)
 - [AcceptOAuth2ConsentRequestSession](docs/AcceptOAuth2ConsentRequestSession.md)
 - [AcceptOAuth2LoginRequest](docs/AcceptOAuth2LoginRequest.md)
 - [CreateJsonWebKeySet](docs/CreateJsonWebKeySet.md)
 - [CreateVerifiableCredentialRequestBody](docs/CreateVerifiableCredentialRequestBody.md)
 - [CredentialSupportedDraft00](docs/CredentialSupportedDraft00.md)
 - [DeviceAuthorization](docs/DeviceAuthorization.md)
 - [DeviceUserAuthRequest](docs/DeviceUserAuthRequest.md)
 - [ErrorOAuth2](docs/ErrorOAuth2.md)
 - [GenericError](docs/GenericError.md)
 - [GetVersion200Response](docs/GetVersion200Response.md)
 - [HealthNotReadyStatus](docs/HealthNotReadyStatus.md)
 - [HealthStatus](docs/HealthStatus.md)
 - [IntrospectedOAuth2Token](docs/IntrospectedOAuth2Token.md)
 - [IsReady200Response](docs/IsReady200Response.md)
 - [IsReady503Response](docs/IsReady503Response.md)
 - [JsonPatch](docs/JsonPatch.md)
 - [JsonWebKey](docs/JsonWebKey.md)
 - [JsonWebKeySet](docs/JsonWebKeySet.md)
 - [KeysetPaginationRequestParameters](docs/KeysetPaginationRequestParameters.md)
 - [KeysetPaginationResponseHeaders](docs/KeysetPaginationResponseHeaders.md)
 - [OAuth2Client](docs/OAuth2Client.md)
 - [OAuth2ClientTokenLifespans](docs/OAuth2ClientTokenLifespans.md)
 - [OAuth2ConsentRequest](docs/OAuth2ConsentRequest.md)
 - [OAuth2ConsentRequestOpenIDConnectContext](docs/OAuth2ConsentRequestOpenIDConnectContext.md)
 - [OAuth2ConsentSession](docs/OAuth2ConsentSession.md)
 - [OAuth2ConsentSessionExpiresAt](docs/OAuth2ConsentSessionExpiresAt.md)
 - [OAuth2LoginRequest](docs/OAuth2LoginRequest.md)
 - [OAuth2LogoutRequest](docs/OAuth2LogoutRequest.md)
 - [OAuth2RedirectTo](docs/OAuth2RedirectTo.md)
 - [OAuth2TokenExchange](docs/OAuth2TokenExchange.md)
 - [OidcConfiguration](docs/OidcConfiguration.md)
 - [OidcUserInfo](docs/OidcUserInfo.md)
 - [RFC6749ErrorJson](docs/RFC6749ErrorJson.md)
 - [RejectOAuth2Request](docs/RejectOAuth2Request.md)
 - [TokenPagination](docs/TokenPagination.md)
 - [TokenPaginationHeaders](docs/TokenPaginationHeaders.md)
 - [TokenPaginationRequestParameters](docs/TokenPaginationRequestParameters.md)
 - [TokenPaginationResponseHeaders](docs/TokenPaginationResponseHeaders.md)
 - [TrustOAuth2JwtGrantIssuer](docs/TrustOAuth2JwtGrantIssuer.md)
 - [TrustedOAuth2JwtGrantIssuer](docs/TrustedOAuth2JwtGrantIssuer.md)
 - [TrustedOAuth2JwtGrantJsonWebKey](docs/TrustedOAuth2JwtGrantJsonWebKey.md)
 - [VerifiableCredentialPrimingResponse](docs/VerifiableCredentialPrimingResponse.md)
 - [VerifiableCredentialProof](docs/VerifiableCredentialProof.md)
 - [VerifiableCredentialResponse](docs/VerifiableCredentialResponse.md)
 - [VerifyUserCodeRequest](docs/VerifyUserCodeRequest.md)
 - [Version](docs/Version.md)


## Documentation For Authorization


Authentication schemes defined for the API:
### basic

- **Type**: HTTP basic authentication

Example

```go
auth := context.WithValue(context.Background(), openapi.ContextBasicAuth, openapi.BasicAuth{
	UserName: "username",
	Password: "password",
})
r, err := client.Service.Operation(auth, args)
```

### bearer

- **Type**: HTTP Bearer token authentication

Example

```go
auth := context.WithValue(context.Background(), openapi.ContextAccessToken, "BEARER_TOKEN_STRING")
r, err := client.Service.Operation(auth, args)
```

### oauth2


- **Type**: OAuth
- **Flow**: accessCode
- **Authorization URL**: https://hydra.demo.ory.sh/oauth2/auth
- **Scopes**: 
 - **offline**: A scope required when requesting refresh tokens (alias for `offline_access`)
 - **offline_access**: A scope required when requesting refresh tokens
 - **openid**: Request an OpenID Connect ID Token

Example

```go
auth := context.WithValue(context.Background(), openapi.ContextAccessToken, "ACCESSTOKENSTRING")
r, err := client.Service.Operation(auth, args)
```

Or via OAuth2 module to automatically refresh tokens and perform user authentication.

```go
import "golang.org/x/oauth2"

/* Perform OAuth2 round trip request and obtain a token */

tokenSource := oauth2cfg.TokenSource(createContext(httpClient), &token)
auth := context.WithValue(oauth2.NoContext, openapi.ContextOAuth2, tokenSource)
r, err := client.Service.Operation(auth, args)
```


## Documentation for Utility Methods

Due to the fact that model structure members are all pointers, this package contains
a number of utility functions to easily obtain pointers to values of basic types.
Each of these functions takes a value of the given basic type and returns a pointer to it:

* `PtrBool`
* `PtrInt`
* `PtrInt32`
* `PtrInt64`
* `PtrFloat`
* `PtrFloat32`
* `PtrFloat64`
* `PtrString`
* `PtrTime`

## Author

hi@ory.sh

