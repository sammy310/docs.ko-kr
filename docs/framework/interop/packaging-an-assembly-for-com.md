---
title: COM용 .NET Framework 어셈블리 패키징
description: COM용 .NET 어셈블리를 패키지합니다. COM 애플리케이션에서 사용할 수 있는 형식 목록, 버전 관리 및 배포 지침, 형식 라이브러리를 수집합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- exposing .NET Framework components to COM
- COM interop, packaging assemblies
- packaging assemblies for COM
- Tlbexp.exe
- TypeLibConverter class
- .NET Services Installation tool
- Assembly Registration tool
- Type Library Exporter
- Reqsvcs.exe
- interoperation with unmanaged code, exposing .NET Framework components
- interoperation with unmanaged code, packaging assemblies
- COM interop, exposing COM components
- Reqasm.exe
ms.assetid: 39dc55aa-f2a1-4093-87bb-f1c0edb6e761
ms.openlocfilehash: 5fde7f7f00aadf4d941d4ffe522453970b67e9e2
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554132"
---
# <a name="packaging-a-net-framework-assembly-for-com"></a><span data-ttu-id="52610-104">COM용 .NET Framework 어셈블리 패키징</span><span class="sxs-lookup"><span data-stu-id="52610-104">Packaging a .NET Framework Assembly for COM</span></span>

<span data-ttu-id="52610-105">COM 개발자는 애플리케이션에 통합하려는 관리 형식에 대한 다음 정보를 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52610-105">COM developers can benefit from the following information about the managed types they plan to incorporate in their application:</span></span>

- <span data-ttu-id="52610-106">COM 애플리케이션에서 사용할 수 있는 형식의 목록</span><span class="sxs-lookup"><span data-stu-id="52610-106">A list of types that COM applications can consume</span></span>

  <span data-ttu-id="52610-107">일부 관리 형식은 COM에 표시되지 않습니다. 일부는 표시되지만 만들 수 없고, 일부는 표시되지도 않고 작성할 수도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="52610-107">Some managed types are invisible to COM; some are visible but not creatable; and some are both visible and creatable.</span></span> <span data-ttu-id="52610-108">어셈블리는 표시되지 않은 형식, 표시되는 형식, 만들 수 없는 형식 및 만들 수 있는 형식의 조합으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="52610-108">An assembly can comprise any combination of invisible, visible, not creatable, and creatable types.</span></span> <span data-ttu-id="52610-109">완성도를 위해 COM에 공개하려는 어셈블리에서 형식을 식별합니다. 해당 형식이 .NET Framework에 공개된 형식의 하위 집합인 경우 특히 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="52610-109">For completeness, identify the types in an assembly that you intend to expose to COM, especially when those types are a subset of the types exposed to the .NET Framework.</span></span>

  <span data-ttu-id="52610-110">자세한 내용은 [상호 운용할 .NET 형식의 정규화](../../standard/native-interop/qualify-net-types-for-interoperation.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="52610-110">For additional information, see [Qualifying .NET Types for Interoperation](../../standard/native-interop/qualify-net-types-for-interoperation.md).</span></span>

- <span data-ttu-id="52610-111">버전 관리 지침</span><span class="sxs-lookup"><span data-stu-id="52610-111">Versioning instructions</span></span>

  <span data-ttu-id="52610-112">클래스 인터페이스(COM interop 생성 인터페이스)를 구현하는 관리 클래스에는 버전 관리 제한 사항이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="52610-112">Managed classes that implement the class interface (a COM interop-generated interface) are subject to versioning restrictions.</span></span>

  <span data-ttu-id="52610-113">클래스 인터페이스를 사용하는 데 대한 지침은 [클래스 인터페이스 소개](../../standard/native-interop/com-callable-wrapper.md#introducing-the-class-interface)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="52610-113">For guidelines on using the class interface, see [Introducing the class interface](../../standard/native-interop/com-callable-wrapper.md#introducing-the-class-interface).</span></span>

- <span data-ttu-id="52610-114">배포 지침</span><span class="sxs-lookup"><span data-stu-id="52610-114">Deployment instructions</span></span>

  <span data-ttu-id="52610-115">게시자가 서명한 강력한 이름의 어셈블리는 전역 어셈블리 캐시에 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52610-115">Strong-named assemblies that are signed by a publisher can be installed into the global assembly cache.</span></span> <span data-ttu-id="52610-116">서명되지 않은 어셈블리는 사용자 컴퓨터에 프라이빗 어셈블리로 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52610-116">Unsigned assemblies must be installed on the user's machine as private assemblies.</span></span>

  <span data-ttu-id="52610-117">자세한 내용은 [어셈블리 보안 고려 사항](../../standard/assembly/security-considerations.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="52610-117">For additional information, see [Assembly Security Considerations](../../standard/assembly/security-considerations.md).</span></span>

- <span data-ttu-id="52610-118">형식 라이브러리 포함</span><span class="sxs-lookup"><span data-stu-id="52610-118">Type library inclusion</span></span>

  <span data-ttu-id="52610-119">COM 애플리케이션에서 사용할 때 대부분의 형식에는 형식 라이브러리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="52610-119">Most types require a type library when consumed by a COM application.</span></span> <span data-ttu-id="52610-120">사용자가 형식 라이브러리를 생성하거나 COM 개발자가 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52610-120">You can generate a type library or have COM developers perform this task.</span></span> <span data-ttu-id="52610-121">Windows SDK에서는 형식 라이브러리를 생성하기 위해 다음 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="52610-121">The Windows SDK provides the following options for generating a type library:</span></span>

  - [<span data-ttu-id="52610-122">형식 라이브러리 내보내기</span><span class="sxs-lookup"><span data-stu-id="52610-122">Type Library Exporter</span></span>](#cpconpackagingassemblyforcomanchor1)

  - [<span data-ttu-id="52610-123">TypeLibConverter 클래스</span><span class="sxs-lookup"><span data-stu-id="52610-123">TypeLibConverter Class</span></span>](#cpconpackagingassemblyforcomanchor2)

  - [<span data-ttu-id="52610-124">어셈블리 등록 도구</span><span class="sxs-lookup"><span data-stu-id="52610-124">Assembly Registration Tool</span></span>](#cpconpackagingassemblyforcomanchor3)

  - [<span data-ttu-id="52610-125">.NET 서비스 설치 도구</span><span class="sxs-lookup"><span data-stu-id="52610-125">.NET Services Installation Tool</span></span>](#cpconpackagingassemblyforcomanchor4)

  <span data-ttu-id="52610-126">선택하는 메커니즘에 관계없이 사용자가 제공하는 어셈블리에 정의된 공용 형식만 생성된 형식 라이브러리에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="52610-126">Regardless of the mechanism you choose, only public types defined in the assembly you supply are included in the generated type library.</span></span>

<span data-ttu-id="52610-127">자세한 내용은 [방법: .NET 기반 애플리케이션에 Win32 리소스로 형식 라이브러리 포함](/previous-versions/dotnet/netframework-4.0/ww9a897z(v=vs.100))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="52610-127">For instructions, see [How to: Embed Type Libraries as Win32 Resources in .NET-Based Applications](/previous-versions/dotnet/netframework-4.0/ww9a897z(v=vs.100)).</span></span>

<a name="cpconpackagingassemblyforcomanchor1"></a>

## <a name="type-library-exporter"></a><span data-ttu-id="52610-128">형식 라이브러리 내보내기</span><span class="sxs-lookup"><span data-stu-id="52610-128">Type Library Exporter</span></span>

<span data-ttu-id="52610-129">[형식 라이브러리 내보내기(Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md)는 어셈블리에 포함된 클래스와 인터페이스를 COM 형식 라이브러리로 변환하는 명령줄 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="52610-129">The [Type Library Exporter (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md) is a command-line tool that converts the classes and interfaces contained in an assembly to a COM type library.</span></span> <span data-ttu-id="52610-130">클래스의 형식 정보를 사용할 수 있으면 COM 클라이언트가 .NET 클래스의 인스턴스를 만들고 COM 개체인 것처럼 인스턴스의 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52610-130">Once the type information of the class is available, COM clients can create an instance of the .NET class and call the methods of the instance, just as if it were a COM object.</span></span> <span data-ttu-id="52610-131">Tlbexp.exe는 한 번에 전체 어셈블리를 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="52610-131">Tlbexp.exe converts an entire assembly at one time.</span></span> <span data-ttu-id="52610-132">Tlbexp.exe를 사용하여 어셈블리에 정의된 형식의 하위 집합에 대한 형식 정보를 생성할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="52610-132">You cannot use Tlbexp.exe to generate type information for a subset of the types defined in an assembly.</span></span>

<a name="cpconpackagingassemblyforcomanchor2"></a>

## <a name="typelibconverter-class"></a><span data-ttu-id="52610-133">TypeLibConverter 클래스</span><span class="sxs-lookup"><span data-stu-id="52610-133">TypeLibConverter Class</span></span>

<span data-ttu-id="52610-134">**System.Runtime.Interop** 네임스페이스에 있는 <xref:System.Runtime.InteropServices.TypeLibConverter> 클래스는 어셈블리에 포함된 클래스와 인터페이스를 COM 형식 라이브러리로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="52610-134">The <xref:System.Runtime.InteropServices.TypeLibConverter> class, located in the **System.Runtime.Interop** namespace, converts the classes and interfaces contained in an assembly to a COM type library.</span></span> <span data-ttu-id="52610-135">이 API는 이전 섹션에 설명된 형식 라이브러리 내보내기와 동일한 형식 정보를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="52610-135">This API produces the same type information as the Type Library Exporter, described in the previous section.</span></span>

<span data-ttu-id="52610-136">**TypeLibConverter 클래스**는 <xref:System.Runtime.InteropServices.ITypeLibConverter>를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="52610-136">The **TypeLibConverter class** implements the <xref:System.Runtime.InteropServices.ITypeLibConverter>.</span></span>

<a name="cpconpackagingassemblyforcomanchor3"></a>

## <a name="assembly-registration-tool"></a><span data-ttu-id="52610-137">어셈블리 등록 도구</span><span class="sxs-lookup"><span data-stu-id="52610-137">Assembly Registration Tool</span></span>

<span data-ttu-id="52610-138">[어셈블리 등록 도구(Regasm.exe)](../tools/regasm-exe-assembly-registration-tool.md)를 사용하면 **/tlb:** 옵션을 적용할 때 형식 라이브러리를 생성하고 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52610-138">The [Assembly Registration Tool (Regasm.exe)](../tools/regasm-exe-assembly-registration-tool.md) can generate and register a type library when you apply the **/tlb:** option.</span></span> <span data-ttu-id="52610-139">COM 클라이언트를 사용하려면 형식 라이브러리가 Windows 레지스트리에 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52610-139">COM clients require that type libraries be installed in the Windows registry.</span></span> <span data-ttu-id="52610-140">이 옵션이 없으면 Regasm.exe는 형식 라이브러리가 아니라 어셈블리에 형식만 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="52610-140">Without this option, Regasm.exe only registers the types in an assembly, not the type library.</span></span> <span data-ttu-id="52610-141">어셈블리에 형식을 등록하고 형식 라이브러리를 등록하는 것은 별개의 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="52610-141">Registering the types in an assembly and registering the type library are distinct activities.</span></span>

<a name="cpconpackagingassemblyforcomanchor4"></a>

## <a name="net-services-installation-tool"></a><span data-ttu-id="52610-142">.NET 서비스 설치 도구</span><span class="sxs-lookup"><span data-stu-id="52610-142">.NET Services Installation Tool</span></span>

<span data-ttu-id="52610-143">[.NET 서비스 설치 도구(Regsvcs.exe)](../tools/regsvcs-exe-net-services-installation-tool.md)는 Windows 2000 구성 요소 서비스를 관리 클래스에 추가하고 여러 작업을 단일 도구에 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="52610-143">The [.NET Services Installation Tool (Regsvcs.exe)](../tools/regsvcs-exe-net-services-installation-tool.md) adds managed classes to Windows 2000 Component Services and combines several tasks within a single tool.</span></span> <span data-ttu-id="52610-144">어셈블리를 로드하고 등록하는 외에도 Regsvcs.exe는 형식 라이브러리를 생성하고 등록하며 기존 COM+ 1.0 애플리케이션에 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52610-144">In addition to loading and registering an assembly, Regsvcs.exe can generate, register, and install the type library into an existing COM+ 1.0 application.</span></span>

## <a name="see-also"></a><span data-ttu-id="52610-145">참조</span><span class="sxs-lookup"><span data-stu-id="52610-145">See also</span></span>

- <xref:System.Runtime.InteropServices.TypeLibConverter>
- <xref:System.Runtime.InteropServices.ITypeLibConverter>
- [<span data-ttu-id="52610-146">.NET Framework 구성 요소를 COM에 노출</span><span class="sxs-lookup"><span data-stu-id="52610-146">Exposing .NET Framework Components to COM</span></span>](exposing-dotnet-components-to-com.md)
- [<span data-ttu-id="52610-147">상호 운용할 .NET 형식의 정규화</span><span class="sxs-lookup"><span data-stu-id="52610-147">Qualifying .NET Types for Interoperation</span></span>](../../standard/native-interop/qualify-net-types-for-interoperation.md)
- [<span data-ttu-id="52610-148">클래스 인터페이스 소개</span><span class="sxs-lookup"><span data-stu-id="52610-148">Introducing the class interface</span></span>](../../standard/native-interop/com-callable-wrapper.md#introducing-the-class-interface)
- [<span data-ttu-id="52610-149">어셈블리 보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="52610-149">Assembly Security Considerations</span></span>](../../standard/assembly/security-considerations.md)
- [<span data-ttu-id="52610-150">Tlbexp.exe(형식 라이브러리 내보내기)</span><span class="sxs-lookup"><span data-stu-id="52610-150">Tlbexp.exe (Type Library Exporter)</span></span>](../tools/tlbexp-exe-type-library-exporter.md)
- [<span data-ttu-id="52610-151">COM에 어셈블리 등록</span><span class="sxs-lookup"><span data-stu-id="52610-151">Registering Assemblies with COM</span></span>](registering-assemblies-with-com.md)
- <span data-ttu-id="52610-152">[방법: 애플리케이션에 Win32 리소스로 형식 라이브러리 포함](/previous-versions/dotnet/netframework-4.0/ww9a897z(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="52610-152">[How to: Embed Type Libraries as Win32 Resources in Applications](/previous-versions/dotnet/netframework-4.0/ww9a897z(v=vs.100))</span></span>
