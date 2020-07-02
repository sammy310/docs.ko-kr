---
title: 어셈블리 및 전역 어셈블리 캐시 사용
description: .NET에서 어셈블리 및 GAC(전역 어셈블리 캐시)로 작업합니다. GAC에서 어셈블리를 설치해야 할 이유를 검토합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- global assembly cache, benefits
- ACLs [.NET Framework]
- GAC (global assembly cache), benefits
- access control lists [.NET Framework]
ms.assetid: 8a18e5c2-d41d-49ef-abcb-7c27e2469433
ms.openlocfilehash: 16cfd9faf02d5b58acad1cc0cf19be61c9814d35
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "85105161"
---
# <a name="working-with-assemblies-and-the-global-assembly-cache"></a><span data-ttu-id="69cd5-104">어셈블리 및 전역 어셈블리 캐시 사용</span><span class="sxs-lookup"><span data-stu-id="69cd5-104">Working with Assemblies and the Global Assembly Cache</span></span>

<span data-ttu-id="69cd5-105">여러 애플리케이션에서 어셈블리를 공유하려면 어셈블리를 전역 어셈블리 캐시에 설치하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69cd5-105">If you intend to share an assembly among several applications, you can install it into the global assembly cache.</span></span> <span data-ttu-id="69cd5-106">공용 언어 런타임이 설치된 각 컴퓨터에는 이 컴퓨터 수준의 코드 캐시가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69cd5-106">Each computer where the common language runtime is installed has this machine-wide code cache.</span></span> <span data-ttu-id="69cd5-107">전역 어셈블리 캐시에는 컴퓨터의 여러 애플리케이션에서 공유하도록 특별히 지정된 어셈블리가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="69cd5-107">The global assembly cache stores assemblies specifically designated to be shared by several applications on the computer.</span></span> <span data-ttu-id="69cd5-108">전역 어셈블리 캐시에 설치하려면 어셈블리에 강력한 이름이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69cd5-108">An assembly must have a strong name to be installed in the global assembly cache.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="69cd5-109">전역 어셈블리 캐시에 배치된 어셈블리에는 같은 어셈블리 이름과 파일 이름(파일 이름 확장명 제외)이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69cd5-109">Assemblies placed in the global assembly cache must have the same assembly name and file name (not including the file name extension).</span></span> <span data-ttu-id="69cd5-110">예를 들어 어셈블리 이름이 myAssembly인 어셈블리의 파일 이름은 myAssembly.exe 또는 myAssembly.dll이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69cd5-110">For example, an assembly with the assembly name of myAssembly must have a file name of either myAssembly.exe or myAssembly.dll.</span></span>  
  
<span data-ttu-id="69cd5-111">필요할 경우에만 어셈블리를 전역 어셈블리 캐시에 설치하여 어셈블리를 공유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69cd5-111">You should share assemblies by installing them into the global assembly cache only when necessary.</span></span> <span data-ttu-id="69cd5-112">일반적으로 어셈블리 공유가 명시적으로 필요하지 않은 경우에는 어셈블리 종속성은 pirvate으로 유지하고 어셈블리를 애플리케이션 디렉터리에 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69cd5-112">As a general guideline, keep assembly dependencies private and locate assemblies in the application directory unless sharing an assembly is explicitly required.</span></span> <span data-ttu-id="69cd5-113">또한 어셈블리가 COM interop 또는 비관리 코드에 액세스 가능하게 설정하기 위해 어셈블리를 전역 어셈블리 캐시에 설치할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="69cd5-113">In addition, you do not have to install assemblies into the global assembly cache to make them accessible to COM interop or unmanaged code.</span></span>  
  
<span data-ttu-id="69cd5-114">어셈블리를 전역 어셈블리 캐시에 설치해야 하는 몇 가지 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="69cd5-114">There are several reasons why you might want to install an assembly into the global assembly cache:</span></span>  
  
- <span data-ttu-id="69cd5-115">공유된 위치.</span><span class="sxs-lookup"><span data-stu-id="69cd5-115">Shared location.</span></span>  
  
     <span data-ttu-id="69cd5-116">애플리케이션에서 사용해야 하는 어셈블리는 전역 어셈블리 캐시에 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69cd5-116">Assemblies that should be used by applications can be put in the global assembly cache.</span></span> <span data-ttu-id="69cd5-117">예를 들어 모든 애플리케이션에서 전역 어셈블리 캐시에 있는 어셈블리를 사용해야 하는 경우 버전 정책 설명을 Machine.config 파일에 추가하여 참조를 어셈블리로 리디렉션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69cd5-117">For example, if all applications should use an assembly located in the global assembly cache, a version policy statement can be added to the Machine.config file that redirects references to the assembly.</span></span>  
  
- <span data-ttu-id="69cd5-118">파일 보안.</span><span class="sxs-lookup"><span data-stu-id="69cd5-118">File security.</span></span>  
  
     <span data-ttu-id="69cd5-119">관리자는 대부분 쓰기 및 실행 액세스를 제어하기 위해 ACL(액세스 제어 목록)을 사용하여 systemroot 디렉터리를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="69cd5-119">Administrators often protect the systemroot directory using an Access Control List (ACL) to control write and execute access.</span></span> <span data-ttu-id="69cd5-120">전역 어셈블리 캐시는 systemroot 디렉터리에 설치되므로 해당 디렉터리의 ACL을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="69cd5-120">Because the global assembly cache is installed in the systemroot directory, it inherits that directory's ACL.</span></span> <span data-ttu-id="69cd5-121">관리자 권한을 가진 사용자만 전역 어셈블리 캐시에서 파일을 삭제하도록 허용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="69cd5-121">It is recommended that only users with Administrator privileges be allowed to delete files from the global assembly cache.</span></span>  
  
- <span data-ttu-id="69cd5-122">Side-by-side 버전 관리.</span><span class="sxs-lookup"><span data-stu-id="69cd5-122">Side-by-side versioning.</span></span>  
  
     <span data-ttu-id="69cd5-123">이름이 같지만 버전 정보가 서로 다른 여러 어셈블리 복사본을 전역 어셈블리 캐시에서 유지 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69cd5-123">Multiple copies of assemblies with the same name but different version information can be maintained in the global assembly cache.</span></span>  
  
- <span data-ttu-id="69cd5-124">추가 검색 위치.</span><span class="sxs-lookup"><span data-stu-id="69cd5-124">Additional search location.</span></span>  
  
     <span data-ttu-id="69cd5-125">공용 언어 런타임은 구성 파일에서 코드베이스 정보를 검색 또는 사용하기 전에 어셈블리 요청과 일치하는 어셈블리가 전역 어셈블리 캐시에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="69cd5-125">The common language runtime checks the global assembly cache for an assembly that matches the assembly request before probing or using the codebase information in a configuration file.</span></span>  
  
 <span data-ttu-id="69cd5-126">어셈블리를 전역 어셈블리 캐시에 명시적으로 설치하지 않으려고 하는 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69cd5-126">Note that there are scenarios where you explicitly do not want to install an assembly into the global assembly cache.</span></span> <span data-ttu-id="69cd5-127">애플리케이션을 구성하는 어셈블리 중 하나를 전역 어셈블리 캐시에 배치하면 XCOPY를 사용하여 애플리케이션 디렉터리를 복사하는 방식으로 애플리케이션을 더 이상 복제하거나 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="69cd5-127">If you place one of the assemblies that make up an application into the global assembly cache, you can no longer replicate or install the application by using XCOPY to copy the application directory.</span></span> <span data-ttu-id="69cd5-128">이 경우 어셈블리를 전역 어셈블리 캐시로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69cd5-128">In this case, you must also move the assembly into the global assembly cache.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="69cd5-129">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="69cd5-129">In This Section</span></span>  
[<span data-ttu-id="69cd5-130">방법: 글로벌 어셈블리 캐시에 어셈블리 설치</span><span class="sxs-lookup"><span data-stu-id="69cd5-130">How to: Install an Assembly into the Global Assembly Cache</span></span>](install-assembly-into-gac.md)  
<span data-ttu-id="69cd5-131">어셈블리를 전역 어셈블리 캐시에 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="69cd5-131">Describes the ways to install an assembly into the global assembly cache.</span></span>  
  
[<span data-ttu-id="69cd5-132">방법: 글로벌 어셈블리 캐시의 내용 보기</span><span class="sxs-lookup"><span data-stu-id="69cd5-132">How to: View the Contents of the Global Assembly Cache</span></span>](how-to-view-the-contents-of-the-gac.md)  
<span data-ttu-id="69cd5-133">[Gacutil.exe(전역 어셈블리 캐시 도구)](../tools/gacutil-exe-gac-tool.md)를 사용하여 전역 어셈블리 캐시의 콘텐츠를 보는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="69cd5-133">Explains how to use the [Gacutil.exe (Global Assembly Cache Tool)](../tools/gacutil-exe-gac-tool.md) to view the contents of the global assembly cache.</span></span>  
  
[<span data-ttu-id="69cd5-134">방법: 글로벌 어셈블리 캐시에서 어셈블리 제거</span><span class="sxs-lookup"><span data-stu-id="69cd5-134">How to: Remove an Assembly from the Global Assembly Cache</span></span>](how-to-remove-an-assembly-from-the-gac.md)  
<span data-ttu-id="69cd5-135">[Gacutil.exe(전역 어셈블리 캐시 도구)](../tools/gacutil-exe-gac-tool.md)를 사용하여 전역 어셈블리 캐시에서 어셈블리를 제거하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="69cd5-135">Explains how to use the [Gacutil.exe (Global Assembly Cache Tool)](../tools/gacutil-exe-gac-tool.md) to remove an assembly from the global assembly cache.</span></span>  
  
[<span data-ttu-id="69cd5-136">전역 어셈블리 캐시에서 서비스되는 구성 요소 사용</span><span class="sxs-lookup"><span data-stu-id="69cd5-136">Using Serviced Components with the Global Assembly Cache</span></span>](use-serviced-components-with-the-gac.md)  
<span data-ttu-id="69cd5-137">서비스되는 구성 요소(관리되는 COM+ 구성 요소)를 전역 어셈블리 캐시에 배치하는 이유를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="69cd5-137">Explains why serviced components (managed COM+ components) should be placed in the global assembly cache.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="69cd5-138">관련 단원</span><span class="sxs-lookup"><span data-stu-id="69cd5-138">Related Sections</span></span>  

[<span data-ttu-id="69cd5-139">어셈블리 만들기</span><span class="sxs-lookup"><span data-stu-id="69cd5-139">Creating Assemblies</span></span>](../../standard/assembly/create.md)  
<span data-ttu-id="69cd5-140">어셈블리 만들기에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="69cd5-140">Provides an overview of creating assemblies.</span></span>  
  
[<span data-ttu-id="69cd5-141">전역 어셈블리 캐시</span><span class="sxs-lookup"><span data-stu-id="69cd5-141">Global Assembly Cache</span></span>](gac.md)  
<span data-ttu-id="69cd5-142">전역 어셈블리 캐시를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="69cd5-142">Describes the global assembly cache.</span></span>  
  
[<span data-ttu-id="69cd5-143">방법: 어셈블리 콘텐츠 보기</span><span class="sxs-lookup"><span data-stu-id="69cd5-143">How to: View Assembly Contents</span></span>](../../standard/assembly/view-contents.md)  
<span data-ttu-id="69cd5-144">[Ildasm.exe(IL 디스어셈블러)](../tools/ildasm-exe-il-disassembler.md)를 사용하여 어셈블리의 MSIL(Microsoft Intermediate Language) 정보를 보는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="69cd5-144">Explains how to use the [Ildasm.exe (IL Disassembler)](../tools/ildasm-exe-il-disassembler.md) to view Microsoft intermediate language (MSIL) information in an assembly.</span></span>  
  
[<span data-ttu-id="69cd5-145">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="69cd5-145">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)  
<span data-ttu-id="69cd5-146">공용 언어 런타임이 애플리케이션을 구성하는 어셈블리를 찾고 로드하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="69cd5-146">Describes how the common language runtime locates and loads the assemblies that make up your application.</span></span>  
  
[<span data-ttu-id="69cd5-147">어셈블리를 사용한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="69cd5-147">Programming with Assemblies</span></span>](../../standard/assembly/index.md)  
<span data-ttu-id="69cd5-148">관리되는 애플리케이션의 빌드 블록인 어셈블리를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="69cd5-148">Describes assemblies, the building blocks of managed applications.</span></span>
