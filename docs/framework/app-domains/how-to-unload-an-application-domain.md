---
title: '방법: 애플리케이션 도메인 언로드'
description: AppDomain.Unload 메서드를 사용하여 지정 애플리케이션 도메인을 정상적으로 종료하는 방법을 통해 .NET에서 애플리케이션 도메인을 언로드하는 방법을 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Unload method
- application domains, unloading
- unloading application domains
ms.assetid: f356116d-e415-4f7c-a332-6e6a60227192
ms.openlocfilehash: b64a9553f63aa4a8deb57f23a97fa464edd64fee
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104679"
---
# <a name="how-to-unload-an-application-domain"></a><span data-ttu-id="4aa24-103">방법: 애플리케이션 도메인 언로드</span><span class="sxs-lookup"><span data-stu-id="4aa24-103">How to: Unload an Application Domain</span></span>
<span data-ttu-id="4aa24-104">애플리케이션 도메인 사용을 마쳤으면 <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> 메서드를 사용하여 언로드합니다.</span><span class="sxs-lookup"><span data-stu-id="4aa24-104">When you have finished using an application domain, unload it using the <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="4aa24-105">**Unload** 메서드는 지정된 애플리케이션 도메인을 정상적으로 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="4aa24-105">The **Unload** method gracefully shuts down the specified application domain.</span></span> <span data-ttu-id="4aa24-106">언로드 프로세스 중에는 새 스레드가 애플리케이션 도메인에 액세스할 수 없으며 모든 애플리케이션 도메인 특정 데이터 구조가 비워집니다.</span><span class="sxs-lookup"><span data-stu-id="4aa24-106">During the unloading process, no new threads can access the application domain, and all application domain–specific data structures are freed.</span></span>  
  
 <span data-ttu-id="4aa24-107">애플리케이션 도메인에 로드된 어셈블리가 제거되고 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4aa24-107">Assemblies loaded into the application domain are removed and are no longer available.</span></span> <span data-ttu-id="4aa24-108">애플리케이션 도메인의 어셈블리가 도메인 중립적인 경우 해당 어셈블리의 데이터는 전체 프로세스가 종료될 때까지 메모리에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4aa24-108">If an assembly in the application domain is domain-neutral, data for the assembly remains in memory until the entire process is shut down.</span></span> <span data-ttu-id="4aa24-109">따라서 도메인 중립 어셈블리를 언로드하려면 전체 프로세스를 종료하는 것이 유일한 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="4aa24-109">There is no mechanism to unload a domain-neutral assembly other than shutting down the entire process.</span></span> <span data-ttu-id="4aa24-110">경우에 따라 애플리케이션 도메인에 대한 언로드 요청이 제대로 작동하지 않아 <xref:System.CannotUnloadAppDomainException>이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4aa24-110">There are situations where the request to unload an application domain does not work and results in a <xref:System.CannotUnloadAppDomainException>.</span></span>  
  
 <span data-ttu-id="4aa24-111">다음 예제에서는 `MyDomain`이라는 새 애플리케이션 도메인을 만들고, 콘솔에 일부 정보를 출력한 다음, 해당 애플리케이션 도메인을 언로드합니다.</span><span class="sxs-lookup"><span data-stu-id="4aa24-111">The following example creates a new application domain called `MyDomain`, prints some information to the console, and then unloads the application domain.</span></span> <span data-ttu-id="4aa24-112">이 코드에서는 언로드된 애플리케이션 도메인의 이름을 콘솔에 출력하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aa24-112">Note that the code then attempts to print the friendly name of the unloaded application domain to the console.</span></span> <span data-ttu-id="4aa24-113">이 동작은 프로그램 끝에 있는 try/catch 문으로 처리되는 예외를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="4aa24-113">This action generates an exception that is handled by the try/catch statements at the end of the program.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4aa24-114">예제</span><span class="sxs-lookup"><span data-stu-id="4aa24-114">Example</span></span>  
 [!code-cpp[System.AppDomain.Load#3](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.appdomain.load/cpp/source3.cpp#3)]
 [!code-csharp[System.AppDomain.Load#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.load/cs/source3.cs#3)]
 [!code-vb[System.AppDomain.Load#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.load/vb/source3.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="4aa24-115">참조</span><span class="sxs-lookup"><span data-stu-id="4aa24-115">See also</span></span>

- [<span data-ttu-id="4aa24-116">애플리케이션 도메인으로 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="4aa24-116">Programming with Application Domains</span></span>](application-domains.md#programming-with-application-domains)
- [<span data-ttu-id="4aa24-117">방법: 애플리케이션 도메인 만들기</span><span class="sxs-lookup"><span data-stu-id="4aa24-117">How to: Create an Application Domain</span></span>](how-to-create-an-application-domain.md)
- [<span data-ttu-id="4aa24-118">애플리케이션 도메인 사용</span><span class="sxs-lookup"><span data-stu-id="4aa24-118">Using Application Domains</span></span>](use.md)
