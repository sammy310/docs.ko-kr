---
title: 어셈블리 매니페스트
ms.date: 08/20/2019
helpviewer_keywords:
- assembly manifest
- dynamic assemblies, assembly manifest
- metadata, assembly manifest
- culture, assembly manifest
- assemblies [.NET Framework], metadata
ms.assetid: 8e40fab9-549d-4731-aec2-ffa47a382de0
ms.openlocfilehash: f1913f8c41ba4a7b54f7abcdfb97400503da8ac5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107148"
---
# <a name="assembly-manifest"></a><span data-ttu-id="ee5c1-102">어셈블리 매니페스트</span><span class="sxs-lookup"><span data-stu-id="ee5c1-102">Assembly manifest</span></span>
<span data-ttu-id="ee5c1-103">정적 또는 동적 어셈블리인지 여부에 상관 없이 모든 어셈블리는 어셈블리의 요소가 서로 어떻게 연관되는지를 설명하는 데이터 컬렉션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5c1-103">Every assembly, whether static or dynamic, contains a collection of data that describes how the elements in the assembly relate to each other.</span></span> <span data-ttu-id="ee5c1-104">이러한 어셈블리 메타데이터는 어셈블리 매니페스트에 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee5c1-104">The assembly manifest contains this assembly metadata.</span></span> <span data-ttu-id="ee5c1-105">어셈블리 매니페스트는 어셈블리의 버전 요구 사항과 보안 ID를 지정하는 데 필요한 모든 메타데이터와 어셈블리의 범위를 정의하고 리소스나 클래스에 대한 참조를 확인하는 데 필요한 모든 메타데이터를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5c1-105">An assembly manifest contains all the metadata needed to specify the assembly's version requirements and security identity, and all metadata needed to define the scope of the assembly and resolve references to resources and classes.</span></span> <span data-ttu-id="ee5c1-106">어셈블리 매니페스트는 MSIL(Microsoft Intermediate Language) 코드가 있는 PE 파일( *.exe* 또는 *.dll*)에 저장되거나 어셈블리 매니페스트 정보만 포함하는 독립 실행형 PE 파일에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee5c1-106">The assembly manifest can be stored in either a PE file (an *.exe* or *.dll*) with Microsoft intermediate language (MSIL) code or in a standalone PE file that contains only assembly manifest information.</span></span>  
  
 <span data-ttu-id="ee5c1-107">다음 예제에서는 매니페스트를 저장하는 여러 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ee5c1-107">The following illustration shows the different ways the manifest can be stored.</span></span>  
  
 ![단일 파일 어셈블리 및 다중 파일 어셈블리 구성에서 매니페스트를 보여주는 다이어그램.](./media/manifest/assembly-types-diagram.gif)  
  
 <span data-ttu-id="ee5c1-109">하나의 연관 파일을 갖는 어셈블리의 경우, 매니페스트는 PE 파일에 포함되어 단일 파일 어셈블리를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5c1-109">For an assembly with one associated file, the manifest is incorporated into the PE file to form a single-file assembly.</span></span> <span data-ttu-id="ee5c1-110">독립 실행형 매니페스트 파일을 만들거나 어셈블리의 PE 파일 중 하나에 매니페스트를 포함시키면 다중 파일 어셈블리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee5c1-110">You can create a multifile assembly with a standalone manifest file or with the manifest incorporated into one of the PE files in the assembly.</span></span>  
  
 <span data-ttu-id="ee5c1-111">각 어셈블리의 매니페스트는 다음 기능을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5c1-111">Each assembly's manifest performs the following functions:</span></span>  
  
- <span data-ttu-id="ee5c1-112">어셈블리를 구성하고 있는 파일을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5c1-112">Enumerates the files that make up the assembly.</span></span>  
  
- <span data-ttu-id="ee5c1-113">어셈블리의 형식 및 리소스로의 참조가 해당 선언 및 구현이 포함된 파일에 매핑되는 방법을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5c1-113">Governs how references to the assembly's types and resources map to the files that contain their declarations and implementations.</span></span>  
  
- <span data-ttu-id="ee5c1-114">어셈블리가 종속된 다른 어셈블리를 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5c1-114">Enumerates other assemblies on which the assembly depends.</span></span>  
  
- <span data-ttu-id="ee5c1-115">어셈블리 소비자와 어셈블리의 구현 정보 간의 간접 참조 수준을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5c1-115">Provides a level of indirection between consumers of the assembly and the assembly's implementation details.</span></span>  
  
- <span data-ttu-id="ee5c1-116">어셈블리가 자체 설명되도록 렌더링합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5c1-116">Renders the assembly self-describing.</span></span>  
  
## <a name="assembly-manifest-contents"></a><span data-ttu-id="ee5c1-117">어셈블리 매니페스트 내용</span><span class="sxs-lookup"><span data-stu-id="ee5c1-117">Assembly manifest contents</span></span>  
 <span data-ttu-id="ee5c1-118">다음 표에서는 어셈블리 매니페스트에 포함되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ee5c1-118">The following table shows the information contained in the assembly manifest.</span></span> <span data-ttu-id="ee5c1-119">어셈블리의 ID는 처음 네 개 항목(어셈블리 이름, 버전 번호, 문화권 및 강력한 이름 정보)으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee5c1-119">The first four items: assembly name, version number, culture, and strong name information make up the assembly's identity.</span></span>  
  
|<span data-ttu-id="ee5c1-120">정보</span><span class="sxs-lookup"><span data-stu-id="ee5c1-120">Information</span></span>|<span data-ttu-id="ee5c1-121">설명</span><span class="sxs-lookup"><span data-stu-id="ee5c1-121">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="ee5c1-122">어셈블리 이름</span><span class="sxs-lookup"><span data-stu-id="ee5c1-122">Assembly name</span></span>|<span data-ttu-id="ee5c1-123">어셈블리의 이름을 나타내는 텍스트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ee5c1-123">A text string specifying the assembly's name.</span></span>|  
|<span data-ttu-id="ee5c1-124">버전 번호</span><span class="sxs-lookup"><span data-stu-id="ee5c1-124">Version number</span></span>|<span data-ttu-id="ee5c1-125">주 버전 번호와 부 버전 번호 및 수정 번호와 빌드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="ee5c1-125">A major and minor version number, and a revision and build number.</span></span> <span data-ttu-id="ee5c1-126">공용 언어 런타임은 이들 번호를 사용하여 버전 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5c1-126">The common language runtime uses these numbers to enforce version policy.</span></span>|  
|<span data-ttu-id="ee5c1-127">문화권</span><span class="sxs-lookup"><span data-stu-id="ee5c1-127">Culture</span></span>|<span data-ttu-id="ee5c1-128">어셈블리에서 지원하는 문화권 또는 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="ee5c1-128">Information on the culture or language the assembly supports.</span></span> <span data-ttu-id="ee5c1-129">이 정보는 특정 어셈블리를 문화권 또는 언어 관련 정보를 포함하는 위성 어셈블리로 지정할 때만 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5c1-129">This information should be used only to designate an assembly as a satellite assembly containing culture- or language-specific information.</span></span> <span data-ttu-id="ee5c1-130">문화권 정보를 포함하는 어셈블리는 자동으로 위성 어셈블리로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee5c1-130">(An assembly with culture information is automatically assumed to be a satellite assembly.)</span></span>|  
|<span data-ttu-id="ee5c1-131">강력한 이름 정보</span><span class="sxs-lookup"><span data-stu-id="ee5c1-131">Strong name information</span></span>|<span data-ttu-id="ee5c1-132">어셈블리에 강력한 이름을 지정하는 경우 게시자의 공개 키.</span><span class="sxs-lookup"><span data-stu-id="ee5c1-132">The public key from the publisher if the assembly has been given a strong name.</span></span>|  
|<span data-ttu-id="ee5c1-133">어셈블리에 포함된 파일 목록</span><span class="sxs-lookup"><span data-stu-id="ee5c1-133">List of all files in the assembly</span></span>|<span data-ttu-id="ee5c1-134">어셈블리에 포함된 각 파일의 해시와 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ee5c1-134">A hash of each file contained in the assembly and a file name.</span></span> <span data-ttu-id="ee5c1-135">어셈블리를 구성하는 모든 파일은 어셈블리 매니페스트가 포함된 파일과 동일한 디렉터리에 위치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5c1-135">Note that all files that make up the assembly must be in the same directory as the file containing the assembly manifest.</span></span>|  
|<span data-ttu-id="ee5c1-136">형식 참조 정보</span><span class="sxs-lookup"><span data-stu-id="ee5c1-136">Type reference information</span></span>|<span data-ttu-id="ee5c1-137">이 정보는 형식 참조를 해당 선언 및 구현이 포함된 파일에 매핑하는 데 사용되며</span><span class="sxs-lookup"><span data-stu-id="ee5c1-137">Information used by the runtime to map a type reference to the file that contains its declaration and implementation.</span></span> <span data-ttu-id="ee5c1-138">어셈블리에서 내보내는 형식에 대해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee5c1-138">This is used for types that are exported from the assembly.</span></span>|  
|<span data-ttu-id="ee5c1-139">참조된 어셈블리에 대한 정보</span><span class="sxs-lookup"><span data-stu-id="ee5c1-139">Information on referenced assemblies</span></span>|<span data-ttu-id="ee5c1-140">어셈블리에서 정적으로 참조하는 다른 어셈블리의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="ee5c1-140">A list of other assemblies that are statically referenced by the assembly.</span></span> <span data-ttu-id="ee5c1-141">각 참조는 종속 어셈블리의 이름, 어셈블리 메타데이터(버전, 문화권, 운영 체제 등) 및 공개 키(강력한 이름의 어셈블리인 경우)를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5c1-141">Each reference includes the dependent assembly's name, assembly metadata (version, culture, operating system, and so on), and public key, if the assembly is strong named.</span></span>|  
  
 <span data-ttu-id="ee5c1-142">코드에서 어셈블리 특성을 사용하여 어셈블리 매니페스트에 있는 정보를 추가하거나 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee5c1-142">You can add or change some information in the assembly manifest by using assembly attributes in your code.</span></span> <span data-ttu-id="ee5c1-143">버전 정보나 정보 특성(상표, 저작권, 제품, 회사, 정보 버전 등)을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee5c1-143">You can change version information and informational attributes, including Trademark, Copyright, Product, Company, and Informational Version.</span></span> <span data-ttu-id="ee5c1-144">어셈블리 특성의 전체 목록은 [어셈블리 특성 설정](set-attributes.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ee5c1-144">For a complete list of assembly attributes, see [Set assembly attributes](set-attributes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee5c1-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ee5c1-145">See also</span></span>

- [<span data-ttu-id="ee5c1-146">어셈블리 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="ee5c1-146">Assembly contents</span></span>](contents.md)
- [<span data-ttu-id="ee5c1-147">어셈블리 버전 관리</span><span class="sxs-lookup"><span data-stu-id="ee5c1-147">Assembly versioning</span></span>](versioning.md)
- [<span data-ttu-id="ee5c1-148">위성 어셈블리 만들기</span><span class="sxs-lookup"><span data-stu-id="ee5c1-148">Create satellite assemblies</span></span>](../../framework/resources/creating-satellite-assemblies-for-desktop-apps.md)
- [<span data-ttu-id="ee5c1-149">강력한 이름의 어셈블리</span><span class="sxs-lookup"><span data-stu-id="ee5c1-149">Strong-named assemblies</span></span>](strong-named.md)
