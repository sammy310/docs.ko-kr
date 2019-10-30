---
title: Fusion 전역 정적 함수
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged global static functions [.NET Framework], fusion
- fusion global static functions [.NET Framework]
- global static functions [.NET Framework fusion]
ms.assetid: 229b2188-9168-4b44-a987-e1f515494688
ms.openlocfilehash: ff94ed23f3e39888b4f7e255feece99898f8aa74
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108264"
---
# <a name="fusion-global-static-functions"></a><span data-ttu-id="8c565-102">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="8c565-102">Fusion Global Static Functions</span></span>
<span data-ttu-id="8c565-103">이 섹션에서는 fusion API에서 사용 하는 관리 되지 않는 전역 정적 함수에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c565-103">This section describes the unmanaged global static functions that the fusion API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8c565-104">단원 내용</span><span class="sxs-lookup"><span data-stu-id="8c565-104">In This Section</span></span>  
 [<span data-ttu-id="8c565-105">ClearDownloadCache 함수</span><span class="sxs-lookup"><span data-stu-id="8c565-105">ClearDownloadCache Function</span></span>](cleardownloadcache-function.md)  
 <span data-ttu-id="8c565-106">다운로드 한 어셈블리의 전역 어셈블리 캐시를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="8c565-106">Clears the global assembly cache of downloaded assemblies.</span></span>  
  
 [<span data-ttu-id="8c565-107">CompareAssemblyIdentity 함수</span><span class="sxs-lookup"><span data-stu-id="8c565-107">CompareAssemblyIdentity Function</span></span>](compareassemblyidentity-function.md)  
 <span data-ttu-id="8c565-108">두 어셈블리 id를 비교 하 여 같은지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c565-108">Compares two assembly identities to determine whether they are equivalent.</span></span>  
  
 [<span data-ttu-id="8c565-109">CreateApplicationContext 함수</span><span class="sxs-lookup"><span data-stu-id="8c565-109">CreateApplicationContext Function</span></span>](createapplicationcontext-function.md)  
 <span data-ttu-id="8c565-110">내부 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="8c565-110">Internal only.</span></span> <span data-ttu-id="8c565-111">이 함수는 .NET Framework 인프라를 지원 하며 사용자 코드에서 직접 사용 하기 위한 것이 아닙니다.)</span><span class="sxs-lookup"><span data-stu-id="8c565-111">(This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="8c565-112">CreateAssemblyCache 함수</span><span class="sxs-lookup"><span data-stu-id="8c565-112">CreateAssemblyCache Function</span></span>](createassemblycache-function.md)  
 <span data-ttu-id="8c565-113">전역 어셈블리 캐시를 나타내는 새 [Iassemblycache](iassemblycache-interface.md) 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8c565-113">Gets a pointer to a new [IAssemblyCache](iassemblycache-interface.md) instance that represents the global assembly cache.</span></span>  
  
 [<span data-ttu-id="8c565-114">CreateAssemblyEnum 함수</span><span class="sxs-lookup"><span data-stu-id="8c565-114">CreateAssemblyEnum Function</span></span>](createassemblyenum-function.md)  
 <span data-ttu-id="8c565-115">지정 된 어셈블리에 존재 하는 개체의 목록을 나타내는 [Iassemblyenum](iassemblyenum-interface.md) 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8c565-115">Gets a pointer to an [IAssemblyEnum](iassemblyenum-interface.md) instance that represents a list of objects that exist in the specified assembly.</span></span>  
  
 [<span data-ttu-id="8c565-116">CreateAssemblyNameObject 함수</span><span class="sxs-lookup"><span data-stu-id="8c565-116">CreateAssemblyNameObject Function</span></span>](createassemblynameobject-function.md)  
 <span data-ttu-id="8c565-117">지정 된 이름을 사용 하 여 어셈블리의 고유 id를 나타내는 [IAssemblyName](iassemblyname-interface.md) 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8c565-117">Gets a pointer to an [IAssemblyName](iassemblyname-interface.md) instance that represents the unique identity of the assembly with the specified name.</span></span>  
  
 [<span data-ttu-id="8c565-118">CreateHistoryReader 함수</span><span class="sxs-lookup"><span data-stu-id="8c565-118">CreateHistoryReader Function</span></span>](createhistoryreader-function.md)  
 <span data-ttu-id="8c565-119">지정 된 파일에 대 한 기록 판독기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8c565-119">Creates a history reader for the specified file.</span></span>  
  
 [<span data-ttu-id="8c565-120">CreateInstallReferenceEnum 함수</span><span class="sxs-lookup"><span data-stu-id="8c565-120">CreateInstallReferenceEnum Function</span></span>](createinstallreferenceenum-function.md)  
 <span data-ttu-id="8c565-121">지정 된 어셈블리에 대 한 응용 프로그램 참조 목록을 나타내는 [Iinstallreferenceenum](iinstallreferenceenum-interface.md) 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8c565-121">Gets a pointer to an [IInstallReferenceEnum](iinstallreferenceenum-interface.md) instance that represents a list of an application's references to the specified assembly.</span></span>  
  
 [<span data-ttu-id="8c565-122">GetAppIdAuthority 함수</span><span class="sxs-lookup"><span data-stu-id="8c565-122">GetAppIdAuthority Function</span></span>](getappidauthority-function.md)  
 <span data-ttu-id="8c565-123">응용 프로그램 id 및 참조에 대 한 키를 관리 하는 [Iappidauthority](iappidauthority-interface.md) 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8c565-123">Gets a pointer to an [IAppIdAuthority](iappidauthority-interface.md) instance that manages keys for application identities and references.</span></span>  
  
 [<span data-ttu-id="8c565-124">GetAssemblyIdentityFromFile 함수</span><span class="sxs-lookup"><span data-stu-id="8c565-124">GetAssemblyIdentityFromFile Function</span></span>](getassemblyidentityfromfile-function.md)  
 <span data-ttu-id="8c565-125">어셈블리에서 지정 된 파일 경로의 지정 된 `IID`를 사용 하 여 `IUnknown` 개체에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8c565-125">Gets a pointer to an `IUnknown` object with the specified `IID` in the assembly at the specified file path.</span></span>  
  
 [<span data-ttu-id="8c565-126">GetCachePath 함수</span><span class="sxs-lookup"><span data-stu-id="8c565-126">GetCachePath Function</span></span>](getcachepath-function.md)  
 <span data-ttu-id="8c565-127">지정 된 플래그를 사용 하 여 캐시 된 어셈블리에 대 한 경로를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8c565-127">Gets the path to the cached assembly, using the specified flags.</span></span>  
  
 [<span data-ttu-id="8c565-128">GetHistoryFileDirectory 함수</span><span class="sxs-lookup"><span data-stu-id="8c565-128">GetHistoryFileDirectory Function</span></span>](gethistoryfiledirectory-function.md)  
 <span data-ttu-id="8c565-129">응용 프로그램 기록 디렉터리의 경로를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c565-129">Retrieves the path of the application history directory.</span></span>  
  
 [<span data-ttu-id="8c565-130">GetIdentityAuthority 함수</span><span class="sxs-lookup"><span data-stu-id="8c565-130">GetIdentityAuthority Function</span></span>](getidentityauthority-function.md)  
 <span data-ttu-id="8c565-131">코드 개체에 대 한 키를 관리 하는 [IIdentityAuthority](iidentityauthority-interface.md) 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8c565-131">Gets a pointer to an [IIdentityAuthority](iidentityauthority-interface.md) instance that manages keys for code objects.</span></span>  
  
 [<span data-ttu-id="8c565-132">IsFrameworkAssembly 함수</span><span class="sxs-lookup"><span data-stu-id="8c565-132">IsFrameworkAssembly Function</span></span>](isframeworkassembly-function.md)  
 <span data-ttu-id="8c565-133">지정 된 어셈블리가 관리 되는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8c565-133">Gets a value that indicates whether the specified assembly is managed.</span></span>  
  
 [<span data-ttu-id="8c565-134">NukeDownloadedCache 함수</span><span class="sxs-lookup"><span data-stu-id="8c565-134">NukeDownloadedCache Function</span></span>](nukedownloadedcache-function.md)  
 <span data-ttu-id="8c565-135">공용 언어 런타임 다운로드 캐시를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c565-135">Deletes the common language runtime download cache.</span></span>  
  
 [<span data-ttu-id="8c565-136">PreBindAssemblyEx 함수</span><span class="sxs-lookup"><span data-stu-id="8c565-136">PreBindAssemblyEx Function</span></span>](prebindassemblyex-function.md)  
 <span data-ttu-id="8c565-137">어셈블리의 정책 후 표시 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8c565-137">Gets the post-policy display name for an assembly.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8c565-138">관련 단원</span><span class="sxs-lookup"><span data-stu-id="8c565-138">Related Sections</span></span>  
 [<span data-ttu-id="8c565-139">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8c565-139">Fusion Interfaces</span></span>](fusion-interfaces.md)  
  
 [<span data-ttu-id="8c565-140">Fusion 열거형</span><span class="sxs-lookup"><span data-stu-id="8c565-140">Fusion Enumerations</span></span>](fusion-enumerations.md)  
  
 [<span data-ttu-id="8c565-141">Fusion 구조체</span><span class="sxs-lookup"><span data-stu-id="8c565-141">Fusion Structures</span></span>](fusion-structures.md)  
  
 [<span data-ttu-id="8c565-142">전역 어셈블리 캐시</span><span class="sxs-lookup"><span data-stu-id="8c565-142">Global Assembly Cache</span></span>](../../app-domains/gac.md)
