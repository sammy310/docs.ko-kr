---
title: '호환성이 손상되는 변경: 사용되지 않고 제거된 API'
description: 사용되지 않고 제거된 API라는 ASP.NET Core 6.0의 호환성이 손상되는 변경에 관한 자세한 정보
author: scottaddie
ms.author: scaddie
ms.date: 02/16/2021
ms.openlocfilehash: 4a4819247b7e6bb957f643b457e651cca5b4e703
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102108406"
---
# <a name="obsoleted-and-removed-apis"></a>사용되지 않고 제거된 API

ASP.NET Core 6.0 미리 보기 1에서는 여러 가지 API가 제거되거나 사용 중단으로 표시되었습니다.

## <a name="version-introduced"></a>도입된 버전

6.0 미리 보기 1

## <a name="old-behavior"></a>이전 동작

ASP.NET Core 5.0에서 해당 API는 제거되었거나 사용되지 않습니다.

## <a name="new-behavior"></a>새 동작

ASP.NET Core 6.0에서 해당 API는 제거되거나 사용되지 않습니다.

## <a name="reason-for-change"></a>변경 이유

해당 API는 더 이상 사용되지 않거나 더 이상 작동하지 않습니다.

## <a name="recommended-action"></a>권장 조치

권장되는 대체 API를 사용합니다.

## <a name="affected-apis"></a>영향을 받는 API

* [Microsoft.AspNetCore.Http.Connections.ParseResponse](/dotnet/api/microsoft.aspnetcore.http.connections.negotiateprotocol.parseresponse?view=aspnetcore-3.1&preserve-view=true#Microsoft_AspNetCore_Http_Connections_NegotiateProtocol_ParseResponse_System_IO_Stream_)가 제거되었습니다. 대신 <xref:Microsoft.AspNetCore.Http.Connections.NegotiateProtocol.ParseResponse(System.ReadOnlySpan{System.Byte})?displayProperty=nameWithType>를 사용하세요.
* [Microsoft.AspNetCore.SignalR.HubInvocationContext](/dotnet/api/microsoft.aspnetcore.signalr.hubinvocationcontext.-ctor?view=aspnetcore-5.0&preserve-view=true#Microsoft_AspNetCore_SignalR_HubInvocationContext__ctor_Microsoft_AspNetCore_SignalR_HubCallerContext_System_String_System_Object___)가 제거되었습니다. 대신 <xref:Microsoft.AspNetCore.SignalR.HubInvocationContext.%23ctor(Microsoft.AspNetCore.SignalR.HubCallerContext,System.IServiceProvider,Microsoft.AspNetCore.SignalR.Hub,System.Reflection.MethodInfo,System.Collections.Generic.IReadOnlyList{System.Object})?displayProperty=nameWithType>를 사용하세요.
* [Microsoft.AspNetCore.Http.Features.IHttpBufferingFeature](/dotnet/api/microsoft.aspnetcore.http.features.ihttpbufferingfeature?view=aspnetcore-3.1&preserve-view=true)가 제거되었습니다. 대신 <xref:Microsoft.AspNetCore.Http.Features.IHttpResponseBodyFeature?displayProperty=nameWithType>를 사용하세요.
* [Microsoft.AspNetCore.Http.Features.IHttpSendFileFeature](/dotnet/api/microsoft.aspnetcore.http.features.ihttpsendfilefeature?view=aspnetcore-3.1&preserve-view=true)가 제거되었습니다. 대신 <xref:Microsoft.AspNetCore.Http.Features.IHttpResponseBodyFeature?displayProperty=nameWithType>를 사용하세요.
* [Microsoft.AspNetCore.StaticFiles.StaticFileResponseContext](/dotnet/api/microsoft.aspnetcore.staticfiles.staticfileresponsecontext.-ctor?view=aspnetcore-3.1&preserve-view=true#Microsoft_AspNetCore_StaticFiles_StaticFileResponseContext__ctor)의 인수 없는 생성자가 제거되었습니다. 대신 <xref:Microsoft.AspNetCore.StaticFiles.StaticFileResponseContext.%23ctor(Microsoft.AspNetCore.Http.HttpContext,Microsoft.Extensions.FileProviders.IFileInfo)?displayProperty=nameWithType>를 사용하세요.
* 생성자 [Microsoft.AspNetCore.Mvc.Infrastructure.ObjectResultExecutor](/dotnet/api/microsoft.aspnetcore.mvc.infrastructure.objectresultexecutor.-ctor?view=aspnetcore-3.1&preserve-view=true#Microsoft_AspNetCore_Mvc_Infrastructure_ObjectResultExecutor__ctor_Microsoft_AspNetCore_Mvc_Infrastructure_OutputFormatterSelector_Microsoft_AspNetCore_Mvc_Infrastructure_IHttpResponseStreamWriterFactory_Microsoft_Extensions_Logging_ILoggerFactory_)가 제거되었습니다. 대신 <xref:Microsoft.AspNetCore.Mvc.Infrastructure.ObjectResultExecutor.%23ctor(Microsoft.AspNetCore.Mvc.Infrastructure.OutputFormatterSelector,Microsoft.AspNetCore.Mvc.Infrastructure.IHttpResponseStreamWriterFactory,Microsoft.Extensions.Logging.ILoggerFactory,Microsoft.Extensions.Options.IOptions{Microsoft.AspNetCore.Mvc.MvcOptions})?displayProperty=nameWithType>를 사용하세요.
* [Microsoft.AspNetCore.Mvc.ModelBinding.ValidationAllowShortCircuitingValidationWhenNoValidatorsArePresent](/dotnet/api/microsoft.aspnetcore.mvc.modelbinding.validation.validationvisitor.allowshortcircuitingvalidationwhennovalidatorsarepresent?view=aspnetcore-3.1&preserve-view=true#Microsoft_AspNetCore_Mvc_ModelBinding_Validation_ValidationVisitor_AllowShortCircuitingValidationWhenNoValidatorsArePresent)가 제거되었습니다.
* [Microsoft.AspNetCore.Mvc.ViewFeatures.ViewComponentResultExecutor](/dotnet/api/microsoft.aspnetcore.mvc.viewfeatures.viewcomponentresultexecutor.-ctor?view=aspnetcore-3.1&preserve-view=true#Microsoft_AspNetCore_Mvc_ViewFeatures_ViewComponentResultExecutor__ctor_Microsoft_Extensions_Options_IOptions_Microsoft_AspNetCore_Mvc_MvcViewOptions__Microsoft_Extensions_Logging_ILoggerFactory_System_Text_Encodings_Web_HtmlEncoder_Microsoft_AspNetCore_Mvc_ModelBinding_IModelMetadataProvider_Microsoft_AspNetCore_Mvc_ViewFeatures_ITempDataDictionaryFactory_)가 제거되었습니다. 대신 <xref:Microsoft.AspNetCore.Mvc.ViewFeatures.ViewComponentResultExecutor.%23ctor(Microsoft.Extensions.Options.IOptions{Microsoft.AspNetCore.Mvc.MvcViewOptions},Microsoft.Extensions.Logging.ILoggerFactory,System.Text.Encodings.Web.HtmlEncoder,Microsoft.AspNetCore.Mvc.ModelBinding.IModelMetadataProvider,Microsoft.AspNetCore.Mvc.ViewFeatures.ITempDataDictionaryFactory,Microsoft.AspNetCore.Mvc.Infrastructure.IHttpResponseStreamWriterFactory)?displayProperty=nameWithType>를 사용하세요.
* 사용되지 않는 [CompatibilityVersion](/dotnet/api/microsoft.aspnetcore.mvc.compatibilityversion?view=aspnetcore-3.1&preserve-view=true)

<!--

## Category

ASP.NET Core

## Affected APIs

- `M:Microsoft.AspNetCore.Http.Connections.NegotiateProtocol.ParseResponse(System.IO.Stream)`
- `M:Microsoft.AspNetCore.SignalR.HubInvocationContext.#ctor(Microsoft.AspNetCore.SignalR.HubCallerContext,System.String,System.Object[])`
- `T:Microsoft.AspNetCore.Http.Features.IHttpBufferingFeature`
- `T:Microsoft.AspNetCore.Http.Features.IHttpSendFileFeature`
- `M:Microsoft.AspNetCore.StaticFiles.StaticFileResponseContext.#ctor`
- `M:Microsoft.AspNetCore.Mvc.Infrastructure.ObjectResultExecutor.#ctor(Microsoft.AspNetCore.Mvc.Infrastructure.OutputFormatterSelector,Microsoft.AspNetCore.Mvc.Infrastructure.IHttpResponseStreamWriterFactory,Microsoft.Extensions.Logging.ILoggerFactory)`
- `Overload:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.AllowShortCircuitingValidationWhenNoValidatorsArePresent`
- `M:Microsoft.AspNetCore.Mvc.ViewFeatures.ViewComponentResultExecutor.#ctor(Microsoft.Extensions.Options.IOptions{Microsoft.AspNetCore.Mvc.MvcViewOptions},Microsoft.Extensions.Logging.ILoggerFactory,System.Text.Encodings.Web.HtmlEncoder,Microsoft.AspNetCore.Mvc.ModelBinding.IModelMetadataProvider,Microsoft.AspNetCore.Mvc.ViewFeatures.ITempDataDictionaryFactory)`
- `T:Microsoft.AspNetCore.Mvc.CompatibilityVersion`

-->
