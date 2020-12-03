---
title: '호환성이 손상되는 변경: 미들웨어: 처리기를 찾을 수 없는 경우 예외 처리기 미들웨어가 원래 예외를 throw함'
description: 'ASP.NET Core 5.0의 호환성이 손상되는 변경에 대해 알아보기. Middleware: 처리기를 찾을 수 없는 경우 예외 처리기 미들웨어가 원래 예외를 throw함'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 8801d3e6950d66fd9f24e051fd8729c50eb0b282
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759978"
---
# <a name="middleware-exception-handler-middleware-throws-original-exception-if-handler-not-found"></a><span data-ttu-id="4793b-103">미들웨어: 처리기를 찾을 수 없는 경우 예외 처리기 미들웨어가 원래 예외를 throw함</span><span class="sxs-lookup"><span data-stu-id="4793b-103">Middleware: Exception Handler Middleware throws original exception if handler not found</span></span>

<span data-ttu-id="4793b-104">ASP.NET Core 5.0 전에 예외 발생 시 [예외 처리기 미들웨어](xref:Microsoft.AspNetCore.Builder.ExceptionHandlerExtensions.UseExceptionHandler%2A)는 구성된 처리기를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4793b-104">Before ASP.NET Core 5.0, the [Exception Handler Middleware](xref:Microsoft.AspNetCore.Builder.ExceptionHandlerExtensions.UseExceptionHandler%2A) executes the configured exception handler when an exception has occurred.</span></span> <span data-ttu-id="4793b-105"><xref:Microsoft.AspNetCore.Builder.ExceptionHandlerOptions.ExceptionHandlingPath>를 통해 구성된 예외 처리기를 찾을 수 없는 경우에는 HTTP 404 응답이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="4793b-105">If the exception handler, configured via <xref:Microsoft.AspNetCore.Builder.ExceptionHandlerOptions.ExceptionHandlingPath>, can't be found, an HTTP 404 response is produced.</span></span> <span data-ttu-id="4793b-106">응답은 다음과 같은 점에서 잘못된 응답입니다.</span><span class="sxs-lookup"><span data-stu-id="4793b-106">The response is misleading in that it:</span></span>

* <span data-ttu-id="4793b-107">사용자 오류인 것 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4793b-107">Seems to be a user error.</span></span>
* <span data-ttu-id="4793b-108">서버에서 예외가 발생했다는 사실을 모호하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="4793b-108">Obscures the fact that an exception occurred on the server.</span></span>

<span data-ttu-id="4793b-109">ASP.NET Core 5.0에서 잘못된 오류를 해결하기 위해 예외 처리기를 찾을 수 없는 경우 `ExceptionHandlerMiddleware`는 원래 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="4793b-109">To address the misleading error in ASP.NET Core 5.0, the `ExceptionHandlerMiddleware` throws the original exception if the exception handler can't be found.</span></span> <span data-ttu-id="4793b-110">따라서 서버에서 HTTP 500 응답이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="4793b-110">As a result, an HTTP 500 response is produced by the server.</span></span> <span data-ttu-id="4793b-111">발생한 오류를 디버그할 때 서버 로그에서 응답을 검토하는 것이 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="4793b-111">The response will be easier to examine in the server logs when debugging the error that occurred.</span></span>

<span data-ttu-id="4793b-112">자세한 내용은 GitHub 이슈 [dotnet/aspnetcore#25288](https://github.com/dotnet/aspnetcore/issues/25288)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4793b-112">For discussion, see GitHub issue [dotnet/aspnetcore#25288](https://github.com/dotnet/aspnetcore/issues/25288).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="4793b-113">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="4793b-113">Version introduced</span></span>

<span data-ttu-id="4793b-114">5.0 RC 1</span><span class="sxs-lookup"><span data-stu-id="4793b-114">5.0 RC 1</span></span>

## <a name="old-behavior"></a><span data-ttu-id="4793b-115">이전 동작</span><span class="sxs-lookup"><span data-stu-id="4793b-115">Old behavior</span></span>

<span data-ttu-id="4793b-116">구성된 예외 처리기를 찾을 수 없는 경우 예외 처리기 미들웨어는 HTTP 404 응답을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="4793b-116">The Exception Handler Middleware produces an HTTP 404 response if the configured exception handler can't be found.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="4793b-117">새 동작</span><span class="sxs-lookup"><span data-stu-id="4793b-117">New behavior</span></span>

<span data-ttu-id="4793b-118">구성된 예외 처리기를 찾을 수 없는 경우 예외 처리기 미들웨어는 원래 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="4793b-118">The Exception Handler Middleware throws the original exception if the configured exception handler can't be found.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="4793b-119">변경 이유</span><span class="sxs-lookup"><span data-stu-id="4793b-119">Reason for change</span></span>

<span data-ttu-id="4793b-120">HTTP 404 오류는 예외가 서버에서 발생했음을 명확히 나타내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4793b-120">The HTTP 404 error doesn't make it obvious that an exception occurred on the server.</span></span> <span data-ttu-id="4793b-121">이 변경으로 인해 다음을 명확히 하는 HTTP 500 오류가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="4793b-121">This change produces an HTTP 500 error to make it obvious that:</span></span>

* <span data-ttu-id="4793b-122">문제가 사용자 오류로 인해 발생하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="4793b-122">The problem isn't caused by a user error.</span></span>
* <span data-ttu-id="4793b-123">서버에서 예외가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="4793b-123">An exception was encountered on the server.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="4793b-124">권장 조치</span><span class="sxs-lookup"><span data-stu-id="4793b-124">Recommended action</span></span>

<span data-ttu-id="4793b-125">API의 변경이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4793b-125">There are no API changes.</span></span> <span data-ttu-id="4793b-126">모든 기존 앱은 계속 컴파일되고 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4793b-126">All existing apps will continue to compile and run.</span></span> <span data-ttu-id="4793b-127">throw된 예외는 서버에서 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="4793b-127">The exception thrown is handled by the server.</span></span> <span data-ttu-id="4793b-128">예를 들어 [Kestrel](/aspnet/core/fundamentals/servers/kestrel) 또는 [HTTP.sys](/aspnet/core/fundamentals/servers/httpsys)에 의해 예외가 HTTP 500 오류 응답으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="4793b-128">For example, the exception is converted to an HTTP 500 error response by [Kestrel](/aspnet/core/fundamentals/servers/kestrel) or [HTTP.sys](/aspnet/core/fundamentals/servers/httpsys).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="4793b-129">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="4793b-129">Affected APIs</span></span>

<span data-ttu-id="4793b-130">없음</span><span class="sxs-lookup"><span data-stu-id="4793b-130">None</span></span>

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
