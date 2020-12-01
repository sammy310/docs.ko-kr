---
title: '방법: 애플리케이션 도메인 구성'
description: .NET에서 애플리케이션 도메인을 구성합니다. AppDomainSetup 클래스를 사용하여 새 애플리케이션 도메인에 대한 구성 정보를 CLR에 제공할 수 있습니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, configuring
- ApplicationBase property
ms.assetid: 07ea8438-7a34-49f0-a7e8-3d6ff7e4a482
ms.openlocfilehash: bbda1f75da6b994c54cd71c56f16615a3758859b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271514"
---
# <a name="how-to-configure-an-application-domain"></a><span data-ttu-id="22d57-104">방법: 애플리케이션 도메인 구성</span><span class="sxs-lookup"><span data-stu-id="22d57-104">How to: Configure an Application Domain</span></span>

<span data-ttu-id="22d57-105"><xref:System.AppDomainSetup> 클래스를 사용하여 새 애플리케이션 도메인에 대한 구성 정보를 공용 언어 런타임에 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22d57-105">You can provide the common language runtime with configuration information for a new application domain using the <xref:System.AppDomainSetup> class.</span></span> <span data-ttu-id="22d57-106">사용자 고유의 애플리케이션 도메인을 만들 때 가장 중요한 속성은 <xref:System.AppDomainSetup.ApplicationBase%2A>입니다.</span><span class="sxs-lookup"><span data-stu-id="22d57-106">When creating your own application domains, the most important property is <xref:System.AppDomainSetup.ApplicationBase%2A>.</span></span> <span data-ttu-id="22d57-107">다른 **AppDomainSetup** 속성은 런타임 호스트에서 특정 애플리케이션 도메인을 구성하는 데 주로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="22d57-107">The other **AppDomainSetup** properties are used mainly by runtime hosts to configure a particular application domain.</span></span>  
  
 <span data-ttu-id="22d57-108">**ApplicationBase** 속성은 애플리케이션의 루트 디렉터리를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="22d57-108">The **ApplicationBase** property defines the root directory of the application.</span></span> <span data-ttu-id="22d57-109">런타임에서 형식 요청을 충족해야 하는 경우 **ApplicationBase** 속성에 지정된 디렉터리에서 해당 형식을 포함하는 어셈블리를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="22d57-109">When the runtime needs to satisfy a type request, it probes for the assembly containing the type in the directory specified by the **ApplicationBase** property.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="22d57-110">새 애플리케이션 도메인은 생성자의 **ApplicationBase** 속성만 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="22d57-110">A new application domain inherits only the **ApplicationBase** property of the creator.</span></span>  
  
 <span data-ttu-id="22d57-111">다음 예제에서는 **AppDomainSetup** 클래스 인스턴스를 만들고, 이 클래스를 사용하여 새 애플리케이션 도메인을 만들고, 콘솔에 정보를 기록한 다음 애플리케이션 도메인을 언로드합니다.</span><span class="sxs-lookup"><span data-stu-id="22d57-111">The following example creates an instance of the **AppDomainSetup** class, uses this class to create a new application domain, writes the information to console, and then unloads the application domain.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22d57-112">예제</span><span class="sxs-lookup"><span data-stu-id="22d57-112">Example</span></span>  

 [!code-cpp[ADApplicationBase#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADApplicationBase/CPP/source2.cpp#2)]
 [!code-csharp[ADApplicationBase#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADApplicationBase/CS/source2.cs#2)]
 [!code-vb[ADApplicationBase#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADApplicationBase/VB/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="22d57-113">참조</span><span class="sxs-lookup"><span data-stu-id="22d57-113">See also</span></span>

- [<span data-ttu-id="22d57-114">애플리케이션 도메인으로 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="22d57-114">Programming with Application Domains</span></span>](application-domains.md#programming-with-application-domains)
- [<span data-ttu-id="22d57-115">애플리케이션 도메인 사용</span><span class="sxs-lookup"><span data-stu-id="22d57-115">Using Application Domains</span></span>](use.md)
