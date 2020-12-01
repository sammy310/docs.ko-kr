---
title: .NET Framework에 COM 구성 요소 노출
description: COM 구성 요소를 .NET에 노출하는 프로세스를 알아봅니다. COM 구성 요소는 중간 계층 비즈니스 애플리케이션 또는 격리된 기능으로서 관리 코드에 유용합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- exposing COM components to .NET Framework
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: e78b14f1-e487-43cd-9c6d-1a07483f1730
ms.openlocfilehash: 4e18e3f49dacbb3a358aa7e9785a5dda93206164
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267067"
---
# <a name="exposing-com-components-to-the-net-framework"></a><span data-ttu-id="f7d7b-104">.NET Framework에 COM 구성 요소 노출</span><span class="sxs-lookup"><span data-stu-id="f7d7b-104">Exposing COM Components to the .NET Framework</span></span>

<span data-ttu-id="f7d7b-105">이 섹션에서는 프로세스를 기존 COM 구성 요소를 관리 코드에 노출하는 데 필요한 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f7d7b-105">This section summarizes the process needed to expose an existing COM component to managed code.</span></span> <span data-ttu-id="f7d7b-106">.NET Framework와 강력하게 통합되는 COM 서버를 작성하는 방법에 대한 자세한 내용은 [상호 운용을 위한 디자인 고려 사항](/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f7d7b-106">For details about writing COM servers that tightly integrate with the .NET Framework, see [Design Considerations for Interoperation](/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100)).</span></span>
  
 <span data-ttu-id="f7d7b-107">기존 COM 구성요소는 중간 계층 비즈니스 애플리케이션 또는 격리된 기능으로서 관리 코드의 중요한 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="f7d7b-107">Existing COM components are valuable resources in managed code as middle-tier business applications or as isolated functionality.</span></span> <span data-ttu-id="f7d7b-108">이상적인 구성 요소는 주 interop 어셈블리를 포함하고 COM을 통해 적용되는 프로그래밍 표준을 엄격하게 준수합니다.</span><span class="sxs-lookup"><span data-stu-id="f7d7b-108">An ideal component has a primary interop assembly and conforms tightly to the programming standards imposed by COM.</span></span>  
  
#### <a name="to-expose-com-components-to-the-net-framework"></a><span data-ttu-id="f7d7b-109">.NET Framework에 COM 구성 요소를 노출하려면</span><span class="sxs-lookup"><span data-stu-id="f7d7b-109">To expose COM components to the .NET Framework</span></span>  
  
1. <span data-ttu-id="f7d7b-110">[형식 라이브러리를 어셈블리로 가져옵니다](importing-a-type-library-as-an-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="f7d7b-110">[Import a type library as an assembly](importing-a-type-library-as-an-assembly.md).</span></span>  
  
     <span data-ttu-id="f7d7b-111">공용 언어 런타임에는 COM 형식을 비롯한 모든 형식에 대한 메타데이터가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f7d7b-111">The common language runtime requires metadata for all types, including COM types.</span></span> <span data-ttu-id="f7d7b-112">메타데이터로 가져온 COM 형식이 포함된 어셈블리를 가져오는 다양한 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7d7b-112">There are several ways to obtain an assembly containing COM types imported as metadata.</span></span>  
  
2. <span data-ttu-id="f7d7b-113">[관리 코드에서 COM 형식을 사용합니다](/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="f7d7b-113">[Use COM types in managed Code](/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)).</span></span>  
  
     <span data-ttu-id="f7d7b-114">관리되는 형식의 경우와 같은 방식으로 COM 형식을 검사하고, 인스턴스를 활성화하고, COM 개체에서 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7d7b-114">You can inspect COM types, activate instances, and invoke methods on the COM object the same way you do for any managed type.</span></span>  
  
3. <span data-ttu-id="f7d7b-115">[Interop 프로젝트를 컴파일합니다](compiling-an-interop-project.md).</span><span class="sxs-lookup"><span data-stu-id="f7d7b-115">[Compile an interop project](compiling-an-interop-project.md).</span></span>  
  
     <span data-ttu-id="f7d7b-116">Windows SDK에서는 Visual Basic, C# 및 C++를 포함하여 CLS(공용 언어 사양)와 호환되는 여러 언어용 컴파일러를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f7d7b-116">The Windows SDK provides compilers for several languages compliant with the Common Language Specification (CLS), including Visual Basic, C#, and C++.</span></span>  
  
4. <span data-ttu-id="f7d7b-117">[Interop 애플리케이션을 배포합니다](deploying-an-interop-application.md).</span><span class="sxs-lookup"><span data-stu-id="f7d7b-117">[Deploy an interop application](deploying-an-interop-application.md).</span></span>  
  
     <span data-ttu-id="f7d7b-118">Interop 애플리케이션은 전역 어셈블리 캐시에 [강력한 이름의](../../standard/assembly/strong-named.md) 서명된 어셈블리로서 가장 잘 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7d7b-118">Interop applications are best deployed as [strong-named](../../standard/assembly/strong-named.md), signed assemblies in the global assembly cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7d7b-119">참조</span><span class="sxs-lookup"><span data-stu-id="f7d7b-119">See also</span></span>

- [<span data-ttu-id="f7d7b-120">비관리 코드와의 상호 운용</span><span class="sxs-lookup"><span data-stu-id="f7d7b-120">Interoperating with Unmanaged Code</span></span>](index.md)
- <span data-ttu-id="f7d7b-121">[상호 운용을 위한 디자인 고려 사항](/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f7d7b-121">[Design Considerations for Interoperation](/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100))</span></span>
- [<span data-ttu-id="f7d7b-122">COM Interop 샘플: .NET 클라이언트 및 COM 서버</span><span class="sxs-lookup"><span data-stu-id="f7d7b-122">COM Interop Sample: .NET Client and COM Server</span></span>](com-interop-sample-net-client-and-com-server.md)
- [<span data-ttu-id="f7d7b-123">언어 독립성 및 언어 독립적 구성 요소</span><span class="sxs-lookup"><span data-stu-id="f7d7b-123">Language Independence and Language-Independent Components</span></span>](../../standard/language-independence-and-language-independent-components.md)
- [<span data-ttu-id="f7d7b-124">Gacutil.exe(전역 어셈블리 캐시 도구)</span><span class="sxs-lookup"><span data-stu-id="f7d7b-124">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../tools/gacutil-exe-gac-tool.md)
