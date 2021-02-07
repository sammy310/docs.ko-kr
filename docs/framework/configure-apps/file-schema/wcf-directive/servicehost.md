---
description: 다음에 대해 자세히 알아보세요. @ServiceHost
title: '@ServiceHost'
ms.date: 03/30/2017
ms.assetid: 96ba6967-00f2-422f-9aa7-15de4d33ebf3
ms.openlocfilehash: d16fda68bdc753121f02f6332dabedf236fac257
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99750314"
---
# <a name="servicehost"></a><span data-ttu-id="487e6-102">\@ServiceHost</span><span class="sxs-lookup"><span data-stu-id="487e6-102">\@ServiceHost</span></span>

<span data-ttu-id="487e6-103">서비스 호스트를 생성하는 데 사용되는 팩터리를 호스트할 서비스 및 .svc 파일에 제공된 호스팅 코드에 액세스하거나 이를 컴파일하는 데 필요한 다른 프로그래밍 요소에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="487e6-103">Associates the factory used to produce the service host with the service to be hosted and other programming aspects required to access or compile the hosting code provided in the .svc file.</span></span>

## <a name="syntax"></a><span data-ttu-id="487e6-104">구문</span><span class="sxs-lookup"><span data-stu-id="487e6-104">Syntax</span></span>

```aspx-csharp
<% @ServiceHost
Service = "Service, ServiceNamespace"
Factory = "Factory, FactoryNamespace"
Debug = "Debug"
Language = "Language"
CodeBehind = "CodeBehind"
%>
```

## <a name="attributes"></a><span data-ttu-id="487e6-105">특성</span><span class="sxs-lookup"><span data-stu-id="487e6-105">Attributes</span></span>

### <a name="service"></a><span data-ttu-id="487e6-106">서비스</span><span class="sxs-lookup"><span data-stu-id="487e6-106">Service</span></span>

<span data-ttu-id="487e6-107">호스트되는 서비스의 CLR 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="487e6-107">The CLR type name of the service hosted.</span></span> <span data-ttu-id="487e6-108">이 이름은 하나 이상의 서비스 계약을 구현하는 형식의 정규화된 이름이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="487e6-108">This should be a qualified name of a type that implements one or more of the service contacts.</span></span>

### <a name="factory"></a><span data-ttu-id="487e6-109">Factory</span><span class="sxs-lookup"><span data-stu-id="487e6-109">Factory</span></span>

<span data-ttu-id="487e6-110">서비스 호스트를 인스턴스화하는 데 사용되는 서비스 호스트 팩터리의 CLR 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="487e6-110">The CLR type name of the service host factory used to instantiate the service host.</span></span> <span data-ttu-id="487e6-111">이 특성은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="487e6-111">This attribute is optional.</span></span> <span data-ttu-id="487e6-112">지정되지 않은 경우 <xref:System.ServiceModel.Activation.ServiceHostFactory>의 인스턴스를 반환하는 <xref:System.ServiceModel.ServiceHost> 기본값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="487e6-112">If unspecified, the default <xref:System.ServiceModel.Activation.ServiceHostFactory> is used, which returns an instance of <xref:System.ServiceModel.ServiceHost>.</span></span>

### <a name="debug"></a><span data-ttu-id="487e6-113">디버그</span><span class="sxs-lookup"><span data-stu-id="487e6-113">Debug</span></span>

<span data-ttu-id="487e6-114">디버그 기호를 사용 하 여 WCF (Windows Communication Foundation) 서비스를 컴파일해야 하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="487e6-114">Indicates whether the Windows Communication Foundation (WCF) service should be compiled with debug symbols.</span></span> <span data-ttu-id="487e6-115">`true` 디버그 기호를 사용 하 여 WCF 서비스를 컴파일해야 하면이 고, 그렇지 않으면입니다. 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="487e6-115">`true` if the WCF service should be compiled with debug symbols; otherwise, `false`.</span></span>

### <a name="language"></a><span data-ttu-id="487e6-116">언어</span><span class="sxs-lookup"><span data-stu-id="487e6-116">Language</span></span>

<span data-ttu-id="487e6-117">파일(.svc) 내의 인라인 코드를 모두 컴파일할 때 사용되는 언어를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="487e6-117">Specifies the language used when compiling all the inline code within file (.svc).</span></span> <span data-ttu-id="487e6-118">값은 any를 나타낼 수 있습니다. , 및를 포함 하 여 `C#` `VB` `JS` c #, Visual Basic 및 JScript .net을 각각 참조 하는 NET 지원 언어.</span><span class="sxs-lookup"><span data-stu-id="487e6-118">The values can represent any .NET-supported language, including `C#`, `VB`, and `JS`, which refer to C#, Visual Basic, and JScript .NET, respectively.</span></span> <span data-ttu-id="487e6-119">이 특성은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="487e6-119">This attribute is optional.</span></span>

### <a name="codebehind"></a><span data-ttu-id="487e6-120">CodeBehind</span><span class="sxs-lookup"><span data-stu-id="487e6-120">CodeBehind</span></span>

<span data-ttu-id="487e6-121">Xml Web services를 구현 하는 클래스가 동일한 파일에 있지 않고 어셈블리로 컴파일되지 않고 *\bin* 디렉터리에 저장 된 경우 xml web services를 구현 하는 소스 파일을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="487e6-121">Specifies the source file that implements the XML Web service, when the class that implements the XML Web service does not reside in the same file and has not been compiled into an assembly and placed in the *\Bin* directory.</span></span>

## <a name="remarks"></a><span data-ttu-id="487e6-122">설명</span><span class="sxs-lookup"><span data-stu-id="487e6-122">Remarks</span></span>

<span data-ttu-id="487e6-123"><xref:System.ServiceModel.ServiceHost>서비스를 호스트 하는 데 사용 되는은 WCF (Windows Communication Foundation) 프로그래밍 모델 내의 확장성 지점입니다.</span><span class="sxs-lookup"><span data-stu-id="487e6-123">The <xref:System.ServiceModel.ServiceHost> used to host the service is a point of extensibility within the Windows Communication Foundation (WCF) programming model.</span></span> <span data-ttu-id="487e6-124">팩터리 패턴은 호스팅 환경에서 직접 인스턴스화하면 안 되는 다형 형식이므로 <xref:System.ServiceModel.ServiceHost>를 인스턴스화하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="487e6-124">A factory pattern is used to instantiate the <xref:System.ServiceModel.ServiceHost> because it is, potentially, a polymorphic type that the hosting environment should not instantiate directly.</span></span>

<span data-ttu-id="487e6-125">기본 구현에서는 <xref:System.ServiceModel.Activation.ServiceHostFactory>를 사용하여 <xref:System.ServiceModel.ServiceHost>의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="487e6-125">The default implementation uses <xref:System.ServiceModel.Activation.ServiceHostFactory> to create an instance of <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="487e6-126">그러나 지시문에 팩터리 구현의 CLR 형식 이름을 지정 하 여 고유한 팩터리 (파생 호스트를 반환 하는 팩터리)를 제공할 수 있습니다 `@ServiceHost` .</span><span class="sxs-lookup"><span data-stu-id="487e6-126">But you can provide your own factory (one that returns your derived host) by specifying the CLR type name of your factory implementation in the `@ServiceHost` directive.</span></span>

<span data-ttu-id="487e6-127">기본 팩터리 대신 사용자 지정 서비스 호스트 팩터리를 사용 하려면 다음과 같이 지시문에 형식 이름을 제공 하면 `@ServiceHost` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="487e6-127">To use you own custom service host factory instead of the default factory, just provide the type name in the `@ServiceHost` directive as follows.</span></span>

```xml
<% @ServiceHost Factory="DerivedFactory" Service="MyService" %>
```

<span data-ttu-id="487e6-128">팩터리 구현을 가능하면 간단하게 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="487e6-128">Keep the factory implementations as light as possible.</span></span> <span data-ttu-id="487e6-129">사용자 지정 논리가 많은 경우 팩터리 내부 대신 호스트 내부에 해당 로직을 배치하면 코드를 재사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="487e6-129">If you have lots of custom logic, your code is more reusable if you put that logic inside your host instead of inside the factory.</span></span>

<span data-ttu-id="487e6-130">예를 들어에 대해 AJAX 사용 끝점을 사용 하도록 설정 하려면 `MyService` <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> `Factory` <xref:System.ServiceModel.Activation.ServiceHostFactory> 다음 예제와 같이 지시문에서 기본값 대신 특성 값에 대해를 지정 합니다 `@ServiceHost` .</span><span class="sxs-lookup"><span data-stu-id="487e6-130">For example, to enable an AJAX-enabled endpoint for `MyService`, specify the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> for the value of the `Factory` attribute, instead of the default <xref:System.ServiceModel.Activation.ServiceHostFactory>, in the `@ServiceHost` directive as shown in the following example:</span></span>

```aspx-csharp
<% @ServiceHost
Service="MyService"
Language="C#"
Debug="true"
Factory="WebScriptServiceHostFactory"
%>
```

## <a name="see-also"></a><span data-ttu-id="487e6-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="487e6-131">See also</span></span>

- [<span data-ttu-id="487e6-132">사용자 지정 서비스 호스트</span><span class="sxs-lookup"><span data-stu-id="487e6-132">Custom Service Host</span></span>](../../../wcf/samples/custom-service-host.md)
