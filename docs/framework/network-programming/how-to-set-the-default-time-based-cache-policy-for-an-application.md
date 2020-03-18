---
title: '방법: 애플리케이션에 대해 시간 기반 캐시 정책 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time-based cache policies
- cache [.NET Framework], time-based policies
- default time-based cache policy
ms.assetid: 6bfce066-a2e7-4add-a05e-85c12ec9f07f
ms.openlocfilehash: 0aaa26f67ef1ef191060e682690fa14de328b812
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048095"
---
# <a name="how-to-set-the-default-time-based-cache-policy-for-an-application"></a><span data-ttu-id="63dc9-102">방법: 애플리케이션에 대해 시간 기반 캐시 정책 설정</span><span class="sxs-lookup"><span data-stu-id="63dc9-102">How to: Set the Default Time-Based Cache Policy for an Application</span></span>
<span data-ttu-id="63dc9-103">기본 시간 기반 캐시 정책을 사용하면 [IETF(Internet Engineering Task Force)](https://www.ietf.org/) 웹 사이트에서 제공되는 RFC 2616의 섹션 13 및 14에 정의된 캐시 동작 및 캐시된 리소스와 함께 전송된 헤더를 통해 정의된 캐시 동작이 애플리케이션에 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63dc9-103">The default time-based cache policy allows an application to have its cache behavior defined by the headers sent with the cached resource and the cache behavior defined in sections 13 and 14 of RFC 2616, available at [Internet Engineering Task Force (IETF)](https://www.ietf.org/) website.</span></span> <span data-ttu-id="63dc9-104">이것은 대부분의 애플리케이션에서 적절한 캐시 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="63dc9-104">This is the appropriate cache behavior for most applications.</span></span>  
  
### <a name="to-set-the-default-automatic-policy-for-an-application"></a><span data-ttu-id="63dc9-105">애플리케이션에 대한 기본 자동 정책을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="63dc9-105">To set the default automatic policy for an application</span></span>  
  
1. <span data-ttu-id="63dc9-106">기본 시간 기반 정책 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="63dc9-106">Create a default time-based policy object.</span></span>  
  
2. <span data-ttu-id="63dc9-107">정책 개체를 애플리케이션 도메인의 기본값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="63dc9-107">Set the policy object as the default for the application domain.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63dc9-108">예제</span><span class="sxs-lookup"><span data-stu-id="63dc9-108">Example</span></span>  
 <span data-ttu-id="63dc9-109">이 섹션의 두 가지 예제는 동일한 정책을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="63dc9-109">The two examples in this section produce identical policies.</span></span>  
  
 <span data-ttu-id="63dc9-110">다음 예제에서는 기본 시간 기반 정책을 만들고 이 정책을 애플리케이션 도메인의 기본값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="63dc9-110">The following example creates a default time-based policy and sets it as the default for the application domain.</span></span>  
  
```csharp  
public static void SetDefaultTimeBasedPolicy ()  
{  
    HttpRequestCachePolicy policy = new HttpRequestCachePolicy ();  
    HttpWebRequest.DefaultCachePolicy = policy ;  
}  
```  
  
```vb  
Public Shared Sub SetDefaultTimeBasedPolicy ()  
    Dim policy = New HttpRequestCachePolicy ()  
    HttpWebRequest.DefaultCachePolicy = policy  
End Sub  
```  
  
 <span data-ttu-id="63dc9-111">다음 예제와 같이 <xref:System.Net.Cache.RequestCachePolicy> 클래스를 사용하여 기본 시간 기반 캐시 정책을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63dc9-111">You can also create the default time-based cache policy using the <xref:System.Net.Cache.RequestCachePolicy> class as shown in the following example:</span></span>  
  
```csharp  
public static void SetDefaultTimeBasedPolicy2()  
{  
    RequestCachePolicy policy = new RequestCachePolicy ();  
    HttpWebRequest.DefaultCachePolicy = policy ;  
}  
```  
  
```vb  
Public Shared Sub SetDefaultTimeBasedPolicy2()  
    Dim policy As New RequestCachePolicy()  
    HttpWebRequest.DefaultCachePolicy = policy  
End Sub  
```  
  
## <a name="see-also"></a><span data-ttu-id="63dc9-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="63dc9-112">See also</span></span>

- [<span data-ttu-id="63dc9-113">네트워크 애플리케이션에 대한 캐시 관리</span><span class="sxs-lookup"><span data-stu-id="63dc9-113">Cache Management for Network Applications</span></span>](cache-management-for-network-applications.md)
- [<span data-ttu-id="63dc9-114">캐시 정책</span><span class="sxs-lookup"><span data-stu-id="63dc9-114">Cache Policy</span></span>](cache-policy.md)
- [<span data-ttu-id="63dc9-115">위치 기반 캐시 정책</span><span class="sxs-lookup"><span data-stu-id="63dc9-115">Location-Based Cache Policies</span></span>](location-based-cache-policies.md)
- [<span data-ttu-id="63dc9-116">시간 기반 캐시 정책</span><span class="sxs-lookup"><span data-stu-id="63dc9-116">Time-Based Cache Policies</span></span>](time-based-cache-policies.md)
- [<span data-ttu-id="63dc9-117">\<requestCaching> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="63dc9-117">\<requestCaching> Element (Network Settings)</span></span>](../configure-apps/file-schema/network/requestcaching-element-network-settings.md)
