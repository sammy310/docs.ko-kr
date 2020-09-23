---
title: COM Interop 소개
ms.date: 07/20/2015
helpviewer_keywords:
- interop assemblies
- COM interop [Visual Basic], about COM interop
ms.assetid: 8bd62e68-383d-407f-998b-29aa0ce0fd67
ms.openlocfilehash: 7bfbf0c6de8519e91a458ab4cbb5693024cdbeb2
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91090393"
---
# <a name="introduction-to-com-interop-visual-basic"></a><span data-ttu-id="7034a-102">COM Interop 소개(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7034a-102">Introduction to COM Interop (Visual Basic)</span></span>

<span data-ttu-id="7034a-103">COM (구성 요소 개체 모델)을 사용 하면 개체가 다른 구성 요소 및 호스트 응용 프로그램에 해당 기능을 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7034a-103">The Component Object Model (COM) lets an object expose its functionality to other components and to host applications.</span></span> <span data-ttu-id="7034a-104">COM 개체는 대부분의 경우 Windows 프로그래밍에 대 한 기본 사항 이지만 CLR (공용 언어 런타임) 용으로 설계 된 응용 프로그램은 다양 한 이점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7034a-104">While COM objects have been fundamental to Windows programming for many years, applications designed for the common language runtime (CLR) offer many advantages.</span></span>  
  
 <span data-ttu-id="7034a-105">.NET Framework 응용 프로그램은 궁극적으로 개발 된 응용 프로그램을 COM으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="7034a-105">.NET Framework applications will eventually replace those developed with COM.</span></span> <span data-ttu-id="7034a-106">그때까지 Visual Studio를 사용 하 여 COM 개체를 사용 하거나 만들어야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7034a-106">Until then, you may have to use or create COM objects by using Visual Studio.</span></span> <span data-ttu-id="7034a-107">COM 또는 *COM interop*와의 상호 운용성을 통해 사용자가 원하는 속도로 .NET Framework으로 전환 하는 동안 기존 com 개체를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7034a-107">Interoperability with COM, or *COM interop*, enables you to use existing COM objects while transitioning to the .NET Framework at your own pace.</span></span>  
  
 <span data-ttu-id="7034a-108">.NET Framework를 사용 하 여 COM 구성 요소를 만들면 등록이 필요 없는 COM interop를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7034a-108">By using the .NET Framework to create COM components, you can use registration-free COM interop.</span></span> <span data-ttu-id="7034a-109">이렇게 하면 컴퓨터에 두 개 이상의 버전이 설치 되어 있을 때 사용할 수 있는 DLL 버전을 제어할 수 있으며, 최종 사용자는 XCOPY 또는 FTP를 사용 하 여 응용 프로그램을 실행할 수 있는 컴퓨터의 적절 한 디렉터리에 응용 프로그램을 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7034a-109">This lets you control which DLL version is enabled when more than one version is installed on a computer, and lets end users use XCOPY or FTP to copy your application to an appropriate directory on their computer where it can be run.</span></span> <span data-ttu-id="7034a-110">자세한 내용은 [등록이 필요 없는 COM Interop](../../../framework/interop/registration-free-com-interop.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7034a-110">For more information, see [Registration-Free COM Interop](../../../framework/interop/registration-free-com-interop.md).</span></span>  
  
## <a name="managed-code-and-data"></a><span data-ttu-id="7034a-111">관리 코드 및 데이터</span><span class="sxs-lookup"><span data-stu-id="7034a-111">Managed Code and Data</span></span>  

 <span data-ttu-id="7034a-112">.NET Framework 용으로 개발 된 코드를 *관리 코드*라고 하며 CLR에서 사용 하는 메타 데이터를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="7034a-112">Code developed for the .NET Framework is referred to as *managed code*, and contains metadata that is used by the CLR.</span></span> <span data-ttu-id="7034a-113">런타임에서 메모리 할당과 회수 및 형식 검사를 수행 하는 등의 데이터 관련 작업을 관리 하기 때문에 .NET Framework 응용 프로그램에서 사용 하는 데이터를 관리 되는 *데이터* 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="7034a-113">Data used by .NET Framework applications is called *managed data* because the runtime manages data-related tasks such as allocating and reclaiming memory and performing type checking.</span></span> <span data-ttu-id="7034a-114">기본적으로 Visual Basic .NET은 관리 코드 및 데이터를 사용 하지만 interop 어셈블리를 사용 하 여 COM 개체의 비관리 코드 및 데이터에 액세스할 수 있습니다 (이 페이지 뒷부분에서 설명).</span><span class="sxs-lookup"><span data-stu-id="7034a-114">By default, Visual Basic .NET uses managed code and data, but you can access the unmanaged code and data of COM objects using interop assemblies (described later on this page).</span></span>  
  
## <a name="assemblies"></a><span data-ttu-id="7034a-115">어셈블리</span><span class="sxs-lookup"><span data-stu-id="7034a-115">Assemblies</span></span>  

 <span data-ttu-id="7034a-116">어셈블리는 .NET Framework 응용 프로그램의 기본 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7034a-116">An assembly is the primary building block of a .NET Framework application.</span></span> <span data-ttu-id="7034a-117">하나 이상의 파일을 포함 하는 단일 구현 단위로 빌드하고, 버전이 지정 되 고, 배포 되는 기능 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="7034a-117">It is a collection of functionality that is built, versioned, and deployed as a single implementation unit containing one or more files.</span></span> <span data-ttu-id="7034a-118">각 어셈블리는 어셈블리 매니페스트를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="7034a-118">Each assembly contains an assembly manifest.</span></span>  
  
## <a name="type-libraries-and-assembly-manifests"></a><span data-ttu-id="7034a-119">형식 라이브러리 및 어셈블리 매니페스트</span><span class="sxs-lookup"><span data-stu-id="7034a-119">Type Libraries and Assembly Manifests</span></span>  

 <span data-ttu-id="7034a-120">형식 라이브러리는 멤버 이름 및 데이터 형식과 같은 COM 개체의 특징을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7034a-120">Type libraries describe characteristics of COM objects, such as member names and data types.</span></span> <span data-ttu-id="7034a-121">어셈블리 매니페스트는 .NET Framework 응용 프로그램에 대해 동일한 기능을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7034a-121">Assembly manifests perform the same function for .NET Framework applications.</span></span> <span data-ttu-id="7034a-122">여기에는 다음에 대 한 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7034a-122">They include information about the following:</span></span>  
  
- <span data-ttu-id="7034a-123">어셈블리 id, 버전, 문화권 및 디지털 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="7034a-123">Assembly identity, version, culture, and digital signature.</span></span>  
  
- <span data-ttu-id="7034a-124">어셈블리 구현을 구성 하는 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="7034a-124">Files that make up the assembly implementation.</span></span>  
  
- <span data-ttu-id="7034a-125">어셈블리를 구성 하는 형식 및 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="7034a-125">Types and resources that make up the assembly.</span></span> <span data-ttu-id="7034a-126">여기에는 여기에서 내보낸 항목이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7034a-126">This includes those that are exported from it.</span></span>  
  
- <span data-ttu-id="7034a-127">다른 어셈블리에 대 한 컴파일 타임 종속성.</span><span class="sxs-lookup"><span data-stu-id="7034a-127">Compile-time dependencies on other assemblies.</span></span>  
  
- <span data-ttu-id="7034a-128">어셈블리를 올바르게 실행 하는 데 필요한 권한입니다.</span><span class="sxs-lookup"><span data-stu-id="7034a-128">Permissions required for the assembly to run correctly.</span></span>  
  
 <span data-ttu-id="7034a-129">어셈블리 및 어셈블리 매니페스트에 대 한 자세한 내용은 [.net의 어셈블리](../../../standard/assembly/index.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7034a-129">For more information about assemblies and assembly manifests, see [Assemblies in .NET](../../../standard/assembly/index.md).</span></span>  
  
### <a name="importing-and-exporting-type-libraries"></a><span data-ttu-id="7034a-130">형식 라이브러리 가져오기 및 내보내기</span><span class="sxs-lookup"><span data-stu-id="7034a-130">Importing and Exporting Type Libraries</span></span>  

 <span data-ttu-id="7034a-131">Visual Studio에는 형식 라이브러리의 정보를 .NET Framework 응용 프로그램으로 가져올 수 있는 Tlbimp 유틸리티인 Tlbimp가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7034a-131">Visual Studio contains a utility, Tlbimp, that lets you import information from a type library into a .NET Framework application.</span></span> <span data-ttu-id="7034a-132">Tlbexp.exe 유틸리티를 사용 하 여 어셈블리에서 형식 라이브러리를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7034a-132">You can generate type libraries from assemblies by using the Tlbexp utility.</span></span>  
  
 <span data-ttu-id="7034a-133">Tlbimp 및 Tlbexp.exe에 대 한 자세한 내용은 [Tlbimp.exe (형식 라이브러리 가져오기)](../../../framework/tools/tlbimp-exe-type-library-importer.md) 및 [Tlbexp.exe (형식 라이브러리 내보내기)](../../../framework/tools/tlbexp-exe-type-library-exporter.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7034a-133">For information about Tlbimp and Tlbexp, see [Tlbimp.exe (Type Library Importer)](../../../framework/tools/tlbimp-exe-type-library-importer.md) and [Tlbexp.exe (Type Library Exporter)](../../../framework/tools/tlbexp-exe-type-library-exporter.md).</span></span>  
  
## <a name="interop-assemblies"></a><span data-ttu-id="7034a-134">Interop 어셈블리</span><span class="sxs-lookup"><span data-stu-id="7034a-134">Interop Assemblies</span></span>  

 <span data-ttu-id="7034a-135">Interop 어셈블리는 관리 코드와 비관리 코드 간에 연결 되는 .NET Framework 어셈블리로, COM 개체 멤버를 동등한 .NET Framework 관리 되는 멤버에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="7034a-135">Interop assemblies are .NET Framework assemblies that bridge between managed and unmanaged code, mapping COM object members to equivalent .NET Framework managed members.</span></span> <span data-ttu-id="7034a-136">Visual Basic .NET에서 만든 Interop 어셈블리는 상호 운용성 마샬링을 비롯 한 COM 개체 작업에 대 한 많은 세부 정보를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="7034a-136">Interop assemblies created by Visual Basic .NET handle many of the details of working with COM objects, such as interoperability marshaling.</span></span>  
  
## <a name="interoperability-marshaling"></a><span data-ttu-id="7034a-137">상호 운용성 마샬링</span><span class="sxs-lookup"><span data-stu-id="7034a-137">Interoperability Marshaling</span></span>  

 <span data-ttu-id="7034a-138">모든 .NET Framework 응용 프로그램은 사용 되는 프로그래밍 언어에 관계 없이 개체의 상호 운용성을 가능 하 게 하는 공용 형식 집합을 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="7034a-138">All .NET Framework applications share a set of common types that enable interoperability of objects, regardless of the programming language that is used.</span></span> <span data-ttu-id="7034a-139">COM 개체의 매개 변수 및 반환 값은 관리 코드에서 사용 되는 것과 다른 데이터 형식을 사용 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7034a-139">The parameters and return values of COM objects sometimes use data types that differ from those used in managed code.</span></span> <span data-ttu-id="7034a-140">*상호 운용성 마샬링은* COM 개체에서 이동 하는 것과 동일한 데이터 형식으로 매개 변수 및 반환 값을 패키징하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="7034a-140">*Interoperability marshaling* is the process of packaging parameters and return values into equivalent data types as they move to and from COM objects.</span></span> <span data-ttu-id="7034a-141">자세한 내용은 [Interop 마샬링](../../../framework/interop/interop-marshaling.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7034a-141">For more information, see [Interop Marshaling](../../../framework/interop/interop-marshaling.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7034a-142">참조</span><span class="sxs-lookup"><span data-stu-id="7034a-142">See also</span></span>

- [<span data-ttu-id="7034a-143">COM Interop</span><span class="sxs-lookup"><span data-stu-id="7034a-143">COM Interop</span></span>](index.md)
- [<span data-ttu-id="7034a-144">연습: COM 개체를 사용한 상속 구현</span><span class="sxs-lookup"><span data-stu-id="7034a-144">Walkthrough: Implementing Inheritance with COM Objects</span></span>](walkthrough-implementing-inheritance-with-com-objects.md)
- [<span data-ttu-id="7034a-145">비관리 코드와의 상호 운용</span><span class="sxs-lookup"><span data-stu-id="7034a-145">Interoperating with Unmanaged Code</span></span>](../../../framework/interop/index.md)
- [<span data-ttu-id="7034a-146">상호 운용성 문제 해결</span><span class="sxs-lookup"><span data-stu-id="7034a-146">Troubleshooting Interoperability</span></span>](troubleshooting-interoperability.md)
- [<span data-ttu-id="7034a-147">.NET 어셈블리</span><span class="sxs-lookup"><span data-stu-id="7034a-147">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="7034a-148">Tlbimp.exe(형식 라이브러리 가져오기)</span><span class="sxs-lookup"><span data-stu-id="7034a-148">Tlbimp.exe (Type Library Importer)</span></span>](../../../framework/tools/tlbimp-exe-type-library-importer.md)
- [<span data-ttu-id="7034a-149">Tlbexp.exe(형식 라이브러리 내보내기)</span><span class="sxs-lookup"><span data-stu-id="7034a-149">Tlbexp.exe (Type Library Exporter)</span></span>](../../../framework/tools/tlbexp-exe-type-library-exporter.md)
- [<span data-ttu-id="7034a-150">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="7034a-150">Interop Marshaling</span></span>](../../../framework/interop/interop-marshaling.md)
- [<span data-ttu-id="7034a-151">등록이 필요 없는 COM interop</span><span class="sxs-lookup"><span data-stu-id="7034a-151">Registration-Free COM Interop</span></span>](../../../framework/interop/registration-free-com-interop.md)
