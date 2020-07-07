---
title: .NET 구성 요소를 COM에 공개
description: COM에 .NET 구성 요소를 공개합니다. 상호 운용할 .NET 형식을 한정합니다. interop 특성을 적용합니다. COM용 어셈블리를 패키지합니다. COM에서 관리되는 형식을 사용합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- exposing .NET Framework components to COM
- interoperation with unmanaged code, exposing .NET Framework components
- COM interop, exposing COM components
ms.assetid: e42a65f7-1e61-411f-b09a-aca1bbce24c6
ms.openlocfilehash: 918c90f6741047f7d3cdf89a9b182700ecb2ed93
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617460"
---
# <a name="exposing-net-components-to-com"></a><span data-ttu-id="f1238-107">.NET 구성 요소를 COM에 공개</span><span class="sxs-lookup"><span data-stu-id="f1238-107">Exposing .NET components to COM</span></span>

<span data-ttu-id="f1238-108">.NET 형식을 작성하고 비관리 코드에서 해당 형식을 사용하는 것은 개발자들에게 독특한 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="f1238-108">Writing a .NET type and consuming that type from unmanaged code are distinct activities for developers.</span></span> <span data-ttu-id="f1238-109">이 섹션에서는 COM 클라이언트와 통합되는 관리 코드를 작성하기 위한 몇 가지 팁을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f1238-109">This section describes several tips for writing managed code that interoperates with COM clients:</span></span>

- <span data-ttu-id="f1238-110">[상호 운용할 .NET 형식을 정규화합니다](../../standard/native-interop/qualify-net-types-for-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="f1238-110">[Qualifying .NET types for interoperation](../../standard/native-interop/qualify-net-types-for-interoperation.md).</span></span>

     <span data-ttu-id="f1238-111">COM에 노출할 모든 관리되는 형식, 메서드, 속성, 필드 및 이벤트는 공용이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1238-111">All managed types, methods, properties, fields, and events that you want to expose to COM must be public.</span></span> <span data-ttu-id="f1238-112">형식에는 COM을 통해 호출될 수 있는 유일한 생성자인 공용 매개 변수가 없는 생성자가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1238-112">Types must have a public parameterless constructor, which is the only constructor that can be invoked through COM.</span></span>

- <span data-ttu-id="f1238-113">[Interop 특성을 적용합니다](../../standard/native-interop/apply-interop-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="f1238-113">[Applying interop attributes](../../standard/native-interop/apply-interop-attributes.md).</span></span>

     <span data-ttu-id="f1238-114">관리 코드 내의 사용자 지정 특성은 구성 요소의 상호 운용성을 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1238-114">Custom attributes within managed code can enhance the interoperability of a component.</span></span>

- <span data-ttu-id="f1238-115">[COM에 대한 어셈블리를 패키지합니다](packaging-an-assembly-for-com.md).</span><span class="sxs-lookup"><span data-stu-id="f1238-115">[Packaging an assembly for COM](packaging-an-assembly-for-com.md).</span></span>

     <span data-ttu-id="f1238-116">COM 개발자는 어셈블리를 참조 및 배포하는 작업에 관련된 단계를 요약하도록 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1238-116">COM developers might require that you summarize the steps involved in referencing and deploying your assemblies.</span></span>

 <span data-ttu-id="f1238-117">또한 이 섹션에서는 COM 클라이언트에서 관리되는 형식을 사용하는 것과 관련된 작업을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f1238-117">Additionally, this section identifies the tasks related to consuming a managed type from a COM client.</span></span>

## <a name="to-consume-a-managed-type-from-com"></a><span data-ttu-id="f1238-118">COM에서 관리되는 형식을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="f1238-118">To consume a managed type from COM</span></span>

1. <span data-ttu-id="f1238-119">[COM에 어셈블리를 등록합니다](registering-assemblies-with-com.md).</span><span class="sxs-lookup"><span data-stu-id="f1238-119">[Register assemblies with COM](registering-assemblies-with-com.md).</span></span>

     <span data-ttu-id="f1238-120">어셈블리의 형식(및 형식 라이브러리)은 디자인 타임에 등록되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1238-120">Types in an assembly (and type libraries) must be registered at design time.</span></span> <span data-ttu-id="f1238-121">설치 관리자가 어셈블리를 등록하지 않으면 COM 개발자에게 Regasm.exe를 사용하도록 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="f1238-121">If an installer does not register the assembly, instruct COM developers to use Regasm.exe.</span></span>

2. <span data-ttu-id="f1238-122">[COM에서 .NET 형식을 참조합니다](how-to-reference-net-types-from-com.md).</span><span class="sxs-lookup"><span data-stu-id="f1238-122">[Reference .NET types from COM](how-to-reference-net-types-from-com.md).</span></span>

     <span data-ttu-id="f1238-123">COM 개발자는 현재 사용하는 동일한 도구와 기술을 통해 어셈블리에서 형식을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1238-123">COM developers can reference types in an assembly using the same tools and techniques they use today.</span></span>

3. <span data-ttu-id="f1238-124">[.NET 개체를 호출합니다](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="f1238-124">[Call a .NET object](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8hw8h46b(v=vs.100)).</span></span>

     <span data-ttu-id="f1238-125">COM 개발자는 관리되는 형식에서 메서드를 호출하는 동일한 방법으로 .NET 개체에서 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1238-125">COM developers can call methods on the .NET object the same way they call methods on any unmanaged type.</span></span> <span data-ttu-id="f1238-126">예를 들어 COM **CoCreateInstance** API는 .NET 개체를 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="f1238-126">For example, the COM **CoCreateInstance** API activates .NET objects.</span></span>

4. <span data-ttu-id="f1238-127">[COM 액세스를 위해 애플리케이션을 배포합니다](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="f1238-127">[Deploy an application for COM access](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/c2850st8(v=vs.100)).</span></span>

     <span data-ttu-id="f1238-128">강력한 이름의 어셈블리는 전역 어셈블리 캐시에 설치할 수 있고 게시자의 시그니처가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f1238-128">A strong-named assembly can be installed in the global assembly cache and requires a signature from its publisher.</span></span> <span data-ttu-id="f1238-129">강력한 이름이 아닌 어셈블리는 클라이언트의 애플리케이션 디렉터리에 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1238-129">Assemblies that are not strong named must be installed in the application directory of the client.</span></span>

## <a name="see-also"></a><span data-ttu-id="f1238-130">참조</span><span class="sxs-lookup"><span data-stu-id="f1238-130">See also</span></span>

- [<span data-ttu-id="f1238-131">비관리 코드와의 상호 운용</span><span class="sxs-lookup"><span data-stu-id="f1238-131">Interoperating with Unmanaged Code</span></span>](index.md)
- [<span data-ttu-id="f1238-132">COM Interop 샘플: COM 클라이언트 및 .NET 서버</span><span class="sxs-lookup"><span data-stu-id="f1238-132">COM Interop Sample: COM Client and .NET Server</span></span>](com-interop-sample-com-client-and-net-server.md)
