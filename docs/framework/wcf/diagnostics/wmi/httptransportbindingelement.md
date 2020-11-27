---
title: HttpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 088a7bce-6bb2-4839-ad74-f68d4b1aa0f9
ms.openlocfilehash: 2be32591c4844cc6d5d0f02916dd1563bb15dc2a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96288790"
---
# <a name="httptransportbindingelement"></a><span data-ttu-id="804c8-102">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="804c8-102">HttpTransportBindingElement</span></span>

<span data-ttu-id="804c8-103">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="804c8-103">HttpTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="804c8-104">구문</span><span class="sxs-lookup"><span data-stu-id="804c8-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="804c8-105">메서드</span><span class="sxs-lookup"><span data-stu-id="804c8-105">Methods</span></span>  

 <span data-ttu-id="804c8-106">HttpTransportBindingElement 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="804c8-106">The HttpTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="804c8-107">속성</span><span class="sxs-lookup"><span data-stu-id="804c8-107">Properties</span></span>  

 <span data-ttu-id="804c8-108">HttpTransportBindingElement 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="804c8-108">The HttpTransportBindingElement class has the following properties:</span></span>  
  
### <a name="allowcookies"></a><span data-ttu-id="804c8-109">AllowCookies</span><span class="sxs-lookup"><span data-stu-id="804c8-109">AllowCookies</span></span>  

 <span data-ttu-id="804c8-110">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="804c8-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="804c8-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="804c8-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="804c8-112">클라이언트가 쿠키를 수락하고 그러한 쿠키를 이후 요청에 전파할지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="804c8-112">A value that indicates whether the client accepts cookies and propagates them on future requests.</span></span>  
  
### <a name="authenticationscheme"></a><span data-ttu-id="804c8-113">AuthenticationScheme</span><span class="sxs-lookup"><span data-stu-id="804c8-113">AuthenticationScheme</span></span>  

 <span data-ttu-id="804c8-114">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="804c8-114">Data type: string</span></span>  
  
 <span data-ttu-id="804c8-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="804c8-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="804c8-116">HTTP 수신기가 처리하는 클라이언트 요청을 인증하는 데 사용되는 인증 스키마입니다.</span><span class="sxs-lookup"><span data-stu-id="804c8-116">The authentication scheme used to authenticate client requests being processed by an HTTP listener.</span></span>  
  
### <a name="bypassproxyonlocal"></a><span data-ttu-id="804c8-117">BypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="804c8-117">BypassProxyOnLocal</span></span>  

 <span data-ttu-id="804c8-118">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="804c8-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="804c8-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="804c8-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="804c8-120">로컬 주소의 프록시를 무시할지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="804c8-120">A value that indicates whether proxies are ignored for local addresses.</span></span>  
  
### <a name="hostnamecomparisonmode"></a><span data-ttu-id="804c8-121">HostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="804c8-121">HostNameComparisonMode</span></span>  

 <span data-ttu-id="804c8-122">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="804c8-122">Data type: string</span></span>  
  
 <span data-ttu-id="804c8-123">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="804c8-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="804c8-124">URI를 일치시킬 때 서비스에 연결하기 위해 호스트 이름이 사용되는지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="804c8-124">A value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>  
  
### <a name="keepaliveenabled"></a><span data-ttu-id="804c8-125">KeepAliveEnabled</span><span class="sxs-lookup"><span data-stu-id="804c8-125">KeepAliveEnabled</span></span>  

 <span data-ttu-id="804c8-126">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="804c8-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="804c8-127">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="804c8-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="804c8-128">선택하면 동작 수준에 상관없이 HTTP 연결이 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="804c8-128">When enabled, HTTP connections are kept alive regardless of activity level.</span></span>  
  
### <a name="maxbuffersize"></a><span data-ttu-id="804c8-129">MaxBufferSize</span><span class="sxs-lookup"><span data-stu-id="804c8-129">MaxBufferSize</span></span>  

 <span data-ttu-id="804c8-130">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="804c8-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="804c8-131">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="804c8-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="804c8-132">버퍼 풀의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="804c8-132">The maximum size of the buffer pool.</span></span>  
  
### <a name="proxyaddress"></a><span data-ttu-id="804c8-133">ProxyAddress</span><span class="sxs-lookup"><span data-stu-id="804c8-133">ProxyAddress</span></span>  

 <span data-ttu-id="804c8-134">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="804c8-134">Data type: string</span></span>  
  
 <span data-ttu-id="804c8-135">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="804c8-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="804c8-136">HTTP 요청에 사용할 프록시의 주소를 포함하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="804c8-136">A URI that contains the address of the proxy to use for HTTP requests.</span></span>  
  
### <a name="proxyauthenticationscheme"></a><span data-ttu-id="804c8-137">ProxyAuthenticationScheme</span><span class="sxs-lookup"><span data-stu-id="804c8-137">ProxyAuthenticationScheme</span></span>  

 <span data-ttu-id="804c8-138">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="804c8-138">Data type: string</span></span>  
  
 <span data-ttu-id="804c8-139">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="804c8-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="804c8-140">HTTP 프록시가 처리하는 클라이언트 체계를 인증하는 데 사용되는 인증 스키마입니다.</span><span class="sxs-lookup"><span data-stu-id="804c8-140">The authentication scheme used to authenticate client requests being processed by an HTTP proxy.</span></span>  
  
### <a name="realm"></a><span data-ttu-id="804c8-141">Realm</span><span class="sxs-lookup"><span data-stu-id="804c8-141">Realm</span></span>  

 <span data-ttu-id="804c8-142">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="804c8-142">Data type: string</span></span>  
  
 <span data-ttu-id="804c8-143">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="804c8-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="804c8-144">인증 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="804c8-144">The authentication realm.</span></span>  
  
### <a name="transfermode"></a><span data-ttu-id="804c8-145">TransferMode</span><span class="sxs-lookup"><span data-stu-id="804c8-145">TransferMode</span></span>  

 <span data-ttu-id="804c8-146">데이터 형식: 문자열</span><span class="sxs-lookup"><span data-stu-id="804c8-146">Data type: string</span></span>  
  
 <span data-ttu-id="804c8-147">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="804c8-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="804c8-148">메시지가 버퍼링되거나 스트리밍되는지 또는 요청이나 응답인지 지정하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="804c8-148">A value that specifies whether messages are buffered or streamed or a request or response.</span></span>  
  
### <a name="unsafeconnectionntlmauthentication"></a><span data-ttu-id="804c8-149">UnsafeConnectionNtlmAuthentication</span><span class="sxs-lookup"><span data-stu-id="804c8-149">UnsafeConnectionNtlmAuthentication</span></span>  

 <span data-ttu-id="804c8-150">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="804c8-150">Data type: boolean</span></span>  
  
 <span data-ttu-id="804c8-151">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="804c8-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="804c8-152">서버에서 안전하지 않은 연결 공유를 사용할 수 있는지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="804c8-152">A value that indicates whether Unsafe Connection Sharing is enabled on the server.</span></span>  
  
### <a name="usedefaultwebproxy"></a><span data-ttu-id="804c8-153">UseDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="804c8-153">UseDefaultWebProxy</span></span>  

 <span data-ttu-id="804c8-154">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="804c8-154">Data type: boolean</span></span>  
  
 <span data-ttu-id="804c8-155">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="804c8-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="804c8-156">사용자별 설정이 아닌 시스템 수준의 프록시 설정을 사용할지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="804c8-156">A value that indicates whether the machine-wide proxy settings are used rather than the user specific settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="804c8-157">요구 사항</span><span class="sxs-lookup"><span data-stu-id="804c8-157">Requirements</span></span>  
  
|<span data-ttu-id="804c8-158">MOF</span><span class="sxs-lookup"><span data-stu-id="804c8-158">MOF</span></span>|<span data-ttu-id="804c8-159">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="804c8-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="804c8-160">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="804c8-160">Namespace</span></span>|<span data-ttu-id="804c8-161">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="804c8-161">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="804c8-162">참고 항목</span><span class="sxs-lookup"><span data-stu-id="804c8-162">See also</span></span>

- <xref:System.ServiceModel.Channels.HttpTransportBindingElement>
