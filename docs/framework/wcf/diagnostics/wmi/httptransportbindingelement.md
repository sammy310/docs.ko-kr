---
description: '자세히 알아보기: HttpTransportBindingElement'
title: HttpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 088a7bce-6bb2-4839-ad74-f68d4b1aa0f9
ms.openlocfilehash: 6c516dd7124d52828145787d55421d12031c2d36
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757373"
---
# <a name="httptransportbindingelement"></a><span data-ttu-id="1eabf-103">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="1eabf-103">HttpTransportBindingElement</span></span>

<span data-ttu-id="1eabf-104">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="1eabf-104">HttpTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1eabf-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="1eabf-105">Syntax</span></span>  
  
```csharp
class HttpTransportBindingElement : TransportBindingElement  
{  
  boolean AllowCookies;  
  string AuthenticationScheme;  
  boolean BypassProxyOnLocal;  
  string HostNameComparisonMode;  
  boolean KeepAliveEnabled;  
  sint32 MaxBufferSize;  
  string ProxyAddress;  
  string ProxyAuthenticationScheme;  
  string Realm;  
  string TransferMode;  
  boolean UnsafeConnectionNtlmAuthentication;  
  boolean UseDefaultWebProxy;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="1eabf-106">메서드</span><span class="sxs-lookup"><span data-stu-id="1eabf-106">Methods</span></span>  

 <span data-ttu-id="1eabf-107">HttpTransportBindingElement 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1eabf-107">The HttpTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="1eabf-108">속성</span><span class="sxs-lookup"><span data-stu-id="1eabf-108">Properties</span></span>  

 <span data-ttu-id="1eabf-109">HttpTransportBindingElement 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eabf-109">The HttpTransportBindingElement class has the following properties:</span></span>  
  
### <a name="allowcookies"></a><span data-ttu-id="1eabf-110">AllowCookies</span><span class="sxs-lookup"><span data-stu-id="1eabf-110">AllowCookies</span></span>  

 <span data-ttu-id="1eabf-111">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="1eabf-111">Data type: boolean</span></span>  
  
 <span data-ttu-id="1eabf-112">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="1eabf-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1eabf-113">클라이언트가 쿠키를 수락하고 그러한 쿠키를 이후 요청에 전파할지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1eabf-113">A value that indicates whether the client accepts cookies and propagates them on future requests.</span></span>  
  
### <a name="authenticationscheme"></a><span data-ttu-id="1eabf-114">AuthenticationScheme</span><span class="sxs-lookup"><span data-stu-id="1eabf-114">AuthenticationScheme</span></span>  

 <span data-ttu-id="1eabf-115">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="1eabf-115">Data type: string</span></span>  
  
 <span data-ttu-id="1eabf-116">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="1eabf-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1eabf-117">HTTP 수신기가 처리하는 클라이언트 요청을 인증하는 데 사용되는 인증 스키마입니다.</span><span class="sxs-lookup"><span data-stu-id="1eabf-117">The authentication scheme used to authenticate client requests being processed by an HTTP listener.</span></span>  
  
### <a name="bypassproxyonlocal"></a><span data-ttu-id="1eabf-118">BypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="1eabf-118">BypassProxyOnLocal</span></span>  

 <span data-ttu-id="1eabf-119">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="1eabf-119">Data type: boolean</span></span>  
  
 <span data-ttu-id="1eabf-120">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="1eabf-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1eabf-121">로컬 주소의 프록시를 무시할지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1eabf-121">A value that indicates whether proxies are ignored for local addresses.</span></span>  
  
### <a name="hostnamecomparisonmode"></a><span data-ttu-id="1eabf-122">HostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="1eabf-122">HostNameComparisonMode</span></span>  

 <span data-ttu-id="1eabf-123">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="1eabf-123">Data type: string</span></span>  
  
 <span data-ttu-id="1eabf-124">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="1eabf-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1eabf-125">URI를 일치시킬 때 서비스에 연결하기 위해 호스트 이름이 사용되는지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1eabf-125">A value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>  
  
### <a name="keepaliveenabled"></a><span data-ttu-id="1eabf-126">KeepAliveEnabled</span><span class="sxs-lookup"><span data-stu-id="1eabf-126">KeepAliveEnabled</span></span>  

 <span data-ttu-id="1eabf-127">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="1eabf-127">Data type: boolean</span></span>  
  
 <span data-ttu-id="1eabf-128">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="1eabf-128">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1eabf-129">선택하면 동작 수준에 상관없이 HTTP 연결이 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eabf-129">When enabled, HTTP connections are kept alive regardless of activity level.</span></span>  
  
### <a name="maxbuffersize"></a><span data-ttu-id="1eabf-130">MaxBufferSize</span><span class="sxs-lookup"><span data-stu-id="1eabf-130">MaxBufferSize</span></span>  

 <span data-ttu-id="1eabf-131">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="1eabf-131">Data type: sint32</span></span>  
  
 <span data-ttu-id="1eabf-132">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="1eabf-132">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1eabf-133">버퍼 풀의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="1eabf-133">The maximum size of the buffer pool.</span></span>  
  
### <a name="proxyaddress"></a><span data-ttu-id="1eabf-134">ProxyAddress</span><span class="sxs-lookup"><span data-stu-id="1eabf-134">ProxyAddress</span></span>  

 <span data-ttu-id="1eabf-135">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="1eabf-135">Data type: string</span></span>  
  
 <span data-ttu-id="1eabf-136">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="1eabf-136">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1eabf-137">HTTP 요청에 사용할 프록시의 주소를 포함하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="1eabf-137">A URI that contains the address of the proxy to use for HTTP requests.</span></span>  
  
### <a name="proxyauthenticationscheme"></a><span data-ttu-id="1eabf-138">ProxyAuthenticationScheme</span><span class="sxs-lookup"><span data-stu-id="1eabf-138">ProxyAuthenticationScheme</span></span>  

 <span data-ttu-id="1eabf-139">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="1eabf-139">Data type: string</span></span>  
  
 <span data-ttu-id="1eabf-140">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="1eabf-140">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1eabf-141">HTTP 프록시가 처리하는 클라이언트 체계를 인증하는 데 사용되는 인증 스키마입니다.</span><span class="sxs-lookup"><span data-stu-id="1eabf-141">The authentication scheme used to authenticate client requests being processed by an HTTP proxy.</span></span>  
  
### <a name="realm"></a><span data-ttu-id="1eabf-142">Realm</span><span class="sxs-lookup"><span data-stu-id="1eabf-142">Realm</span></span>  

 <span data-ttu-id="1eabf-143">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="1eabf-143">Data type: string</span></span>  
  
 <span data-ttu-id="1eabf-144">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="1eabf-144">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1eabf-145">인증 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="1eabf-145">The authentication realm.</span></span>  
  
### <a name="transfermode"></a><span data-ttu-id="1eabf-146">TransferMode</span><span class="sxs-lookup"><span data-stu-id="1eabf-146">TransferMode</span></span>  

 <span data-ttu-id="1eabf-147">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="1eabf-147">Data type: string</span></span>  
  
 <span data-ttu-id="1eabf-148">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="1eabf-148">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1eabf-149">메시지가 버퍼링되거나 스트리밍되는지 또는 요청이나 응답인지 지정하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1eabf-149">A value that specifies whether messages are buffered or streamed or a request or response.</span></span>  
  
### <a name="unsafeconnectionntlmauthentication"></a><span data-ttu-id="1eabf-150">UnsafeConnectionNtlmAuthentication</span><span class="sxs-lookup"><span data-stu-id="1eabf-150">UnsafeConnectionNtlmAuthentication</span></span>  

 <span data-ttu-id="1eabf-151">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="1eabf-151">Data type: boolean</span></span>  
  
 <span data-ttu-id="1eabf-152">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="1eabf-152">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1eabf-153">서버에서 안전하지 않은 연결 공유를 사용할 수 있는지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1eabf-153">A value that indicates whether Unsafe Connection Sharing is enabled on the server.</span></span>  
  
### <a name="usedefaultwebproxy"></a><span data-ttu-id="1eabf-154">UseDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="1eabf-154">UseDefaultWebProxy</span></span>  

 <span data-ttu-id="1eabf-155">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="1eabf-155">Data type: boolean</span></span>  
  
 <span data-ttu-id="1eabf-156">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="1eabf-156">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1eabf-157">사용자별 설정이 아닌 시스템 수준의 프록시 설정을 사용할지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1eabf-157">A value that indicates whether the machine-wide proxy settings are used rather than the user specific settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1eabf-158">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1eabf-158">Requirements</span></span>  
  
|<span data-ttu-id="1eabf-159">MOF</span><span class="sxs-lookup"><span data-stu-id="1eabf-159">MOF</span></span>|<span data-ttu-id="1eabf-160">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eabf-160">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="1eabf-161">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="1eabf-161">Namespace</span></span>|<span data-ttu-id="1eabf-162">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1eabf-162">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1eabf-163">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1eabf-163">See also</span></span>

- <xref:System.ServiceModel.Channels.HttpTransportBindingElement>
