---
description: 다음에 대해 자세히 알아보세요. <behaviorExtensions>
title: <behaviorExtensions>
ms.date: 03/30/2017
ms.assetid: 59f2791a-c78f-40d7-aa80-0d9cd10135d9
ms.openlocfilehash: 0bd641f8e26d309c592c07bcc19ff02897fe71cd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639525"
---
# \<behaviorExtensions>

<span data-ttu-id="4d5d5-102">동작 확장을 사용하면 사용자 정의 동작 요소를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d5d5-102">Behavior extensions enable the user to create user-defined behavior elements.</span></span> <span data-ttu-id="4d5d5-103">이러한 요소는 표준 WCF(Windows Communication Foundation) 동작 요소 구성과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d5d5-103">These elements can be used alongside the standard Windows Communication Foundation (WCF) behavior elements.</span></span> <span data-ttu-id="4d5d5-104">`behaviorExtensions` 섹션은 구성에 사용할 수 있도록 요소를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5d5-104">The `behaviorExtensions` section defines the element such that it can be used in configuration.</span></span> <span data-ttu-id="4d5d5-105">다음은 일반적인 동작 확장 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="4d5d5-105">Here is an example of a typical behavior extension.</span></span>  
  
```xml  
<system.serviceModel>
  <extensions>
    <behaviorExtensions>
      <add name="myBehavior"
           type="Microsoft.ServiceModel.Samples.MyBehaviorSection, MyBehavior,
                 Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />
    </behaviorExtensions>
  </extensions>
</system.serviceModel>
```  
  
 <span data-ttu-id="4d5d5-106">요소에 구성 기능을 추가하려면 구성 요소를 작성하고 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5d5-106">To add configuration abilities to the element, you need to write and register a configuration element.</span></span> <span data-ttu-id="4d5d5-107">이에 대한 자세한 내용은 <xref:System.Configuration> 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4d5d5-107">For more information on this, see the <xref:System.Configuration> documentation.</span></span>  
  
 <span data-ttu-id="4d5d5-108">요소 및 해당 구성 형식이 정의되면 다음 예제와 같이 확장을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d5d5-108">After the element and its configuration type are defined, the extension can be used, as shown in the following example.</span></span>  
  
```xml  
<behaviors>
  <behavior configurationName="testChannelBehavior">
    <myBehavior />
    <channelSecurity cacheCookies="false"
                     detectReplays="false"
                     maxCachedNonces="9"
                     maxClockSkew="00:00:03"
                     maxCookieCachingTime="00:07:24"
                     replayWindow="00:07:22.2190000" />
  </behavior>
</behaviors>
```  
  
## <a name="security"></a><span data-ttu-id="4d5d5-109">보안</span><span class="sxs-lookup"><span data-stu-id="4d5d5-109">Security</span></span>  

 <span data-ttu-id="4d5d5-110">`machine.config` 및 `app.config` 파일에 형식을 등록할 때는 정규화된 어셈블리 이름을 사용할 것을 강력히 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5d5-110">It is strongly recommended that you use fully qualified assembly names when registering types in the `machine.config` and `app.config` files.</span></span> <span data-ttu-id="4d5d5-111">형식이 고유하게 정의되지 않으면 CLR 형식 로더는 다음 위치에서 지정한 순서로 형식을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5d5-111">If the type is not uniquely defined, the CLR type loader searches for it in the following locations in the specified order:</span></span>  
  
 <span data-ttu-id="4d5d5-112">형식의 어셈블리를 알 수 있으면 로더는 구성 파일의 리디렉션 위치, GAC, 현재 어셈블리(구성 정보 사용) 및 애플리케이션 기본 디렉터리를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5d5-112">If the assembly of the type is known, the loader searches the configuration file's redirect locations, GAC, the current assembly using configuration information, and the application base directory.</span></span> <span data-ttu-id="4d5d5-113">어셈블리를 알 수 없으면 로더는 현재 어셈블리, mscorlib 및 `TypeResolve` 이벤트 처리기가 반환한 위치를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5d5-113">If the assembly is unknown, the loader searches the current assembly, mscorlib, and the location returned by the `TypeResolve` event handler.</span></span> <span data-ttu-id="4d5d5-114">CLR 검색 순서는 형식 전달 메커니즘 및 AppDomain.TypeResolve 이벤트와 같은 후크로 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d5d5-114">This CLR search order can be modified with hooks such as the Type Forwarding mechanism and the AppDomain.TypeResolve event.</span></span>  
  
 <span data-ttu-id="4d5d5-115">공격자는 CLR 검색 순서를 탐색하고 허가되지 않은 코드를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d5d5-115">An attacker can exploit the CLR search order and execute unauthorized code.</span></span> <span data-ttu-id="4d5d5-116">정규화된(강력한) 이름을 사용하면 형식을 고유하게 식별하고 시스템 보안을 더욱 강화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d5d5-116">Using fully qualified (strong) names uniquely identifies a type and further increases security of your system.</span></span>  
  
 <span data-ttu-id="4d5d5-117">자세한 내용은 [런타임에서 어셈블리를 찾는 방법](../../../deployment/how-the-runtime-locates-assemblies.md) 및을 참조 하십시오 <xref:System.AppDomain.TypeResolve> .</span><span class="sxs-lookup"><span data-stu-id="4d5d5-117">For more information, see [How the Runtime Locates Assemblies](../../../deployment/how-the-runtime-locates-assemblies.md) and <xref:System.AppDomain.TypeResolve>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d5d5-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4d5d5-118">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>
- [<span data-ttu-id="4d5d5-119">동작을 사용하여 런타임 구성 및 확장</span><span class="sxs-lookup"><span data-stu-id="4d5d5-119">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
