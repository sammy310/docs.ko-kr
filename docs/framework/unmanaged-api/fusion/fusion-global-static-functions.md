---
description: '자세히 알아보기: Fusion 전역 정적 함수'
title: Fusion 전역 정적 함수
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged global static functions [.NET Framework], fusion
- fusion global static functions [.NET Framework]
- global static functions [.NET Framework fusion]
ms.assetid: 229b2188-9168-4b44-a987-e1f515494688
ms.openlocfilehash: c696908f72d67ecff5e7383e7a2754dd5436b819
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761085"
---
# <a name="fusion-global-static-functions"></a><span data-ttu-id="d0d3c-103">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="d0d3c-103">Fusion Global Static Functions</span></span>

<span data-ttu-id="d0d3c-104">이 섹션에서는 fusion API에서 사용 하는 관리 되지 않는 전역 정적 함수에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0d3c-104">This section describes the unmanaged global static functions that the fusion API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d0d3c-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="d0d3c-105">In This Section</span></span>  

 [<span data-ttu-id="d0d3c-106">ClearDownloadCache 함수</span><span class="sxs-lookup"><span data-stu-id="d0d3c-106">ClearDownloadCache Function</span></span>](cleardownloadcache-function.md)  
 <span data-ttu-id="d0d3c-107">다운로드 한 어셈블리의 전역 어셈블리 캐시를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="d0d3c-107">Clears the global assembly cache of downloaded assemblies.</span></span>  
  
 [<span data-ttu-id="d0d3c-108">CompareAssemblyIdentity 함수</span><span class="sxs-lookup"><span data-stu-id="d0d3c-108">CompareAssemblyIdentity Function</span></span>](compareassemblyidentity-function.md)  
 <span data-ttu-id="d0d3c-109">두 어셈블리 id를 비교 하 여 같은지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0d3c-109">Compares two assembly identities to determine whether they are equivalent.</span></span>  
  
 [<span data-ttu-id="d0d3c-110">CreateApplicationContext 함수</span><span class="sxs-lookup"><span data-stu-id="d0d3c-110">CreateApplicationContext Function</span></span>](createapplicationcontext-function.md)  
 <span data-ttu-id="d0d3c-111">내부 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="d0d3c-111">Internal only.</span></span> <span data-ttu-id="d0d3c-112">이 함수는 .NET Framework 인프라를 지원 하며 사용자 코드에서 직접 사용 하기 위한 것이 아닙니다.)</span><span class="sxs-lookup"><span data-stu-id="d0d3c-112">(This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.)</span></span>  
  
 [<span data-ttu-id="d0d3c-113">CreateAssemblyCache 함수</span><span class="sxs-lookup"><span data-stu-id="d0d3c-113">CreateAssemblyCache Function</span></span>](createassemblycache-function.md)  
 <span data-ttu-id="d0d3c-114">전역 어셈블리 캐시를 나타내는 새 [Iassemblycache](iassemblycache-interface.md) 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d0d3c-114">Gets a pointer to a new [IAssemblyCache](iassemblycache-interface.md) instance that represents the global assembly cache.</span></span>  
  
 [<span data-ttu-id="d0d3c-115">CreateAssemblyEnum 함수</span><span class="sxs-lookup"><span data-stu-id="d0d3c-115">CreateAssemblyEnum Function</span></span>](createassemblyenum-function.md)  
 <span data-ttu-id="d0d3c-116">지정 된 어셈블리에 존재 하는 개체의 목록을 나타내는 [Iassemblyenum](iassemblyenum-interface.md) 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d0d3c-116">Gets a pointer to an [IAssemblyEnum](iassemblyenum-interface.md) instance that represents a list of objects that exist in the specified assembly.</span></span>  
  
 [<span data-ttu-id="d0d3c-117">CreateAssemblyNameObject 함수</span><span class="sxs-lookup"><span data-stu-id="d0d3c-117">CreateAssemblyNameObject Function</span></span>](createassemblynameobject-function.md)  
 <span data-ttu-id="d0d3c-118">지정 된 이름을 사용 하 여 어셈블리의 고유 id를 나타내는 [IAssemblyName](iassemblyname-interface.md) 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d0d3c-118">Gets a pointer to an [IAssemblyName](iassemblyname-interface.md) instance that represents the unique identity of the assembly with the specified name.</span></span>  
  
 [<span data-ttu-id="d0d3c-119">CreateHistoryReader 함수</span><span class="sxs-lookup"><span data-stu-id="d0d3c-119">CreateHistoryReader Function</span></span>](createhistoryreader-function.md)  
 <span data-ttu-id="d0d3c-120">지정 된 파일에 대 한 기록 판독기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d0d3c-120">Creates a history reader for the specified file.</span></span>  
  
 [<span data-ttu-id="d0d3c-121">CreateInstallReferenceEnum 함수</span><span class="sxs-lookup"><span data-stu-id="d0d3c-121">CreateInstallReferenceEnum Function</span></span>](createinstallreferenceenum-function.md)  
 <span data-ttu-id="d0d3c-122">지정 된 어셈블리에 대 한 응용 프로그램 참조 목록을 나타내는 [Iinstallreferenceenum](iinstallreferenceenum-interface.md) 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d0d3c-122">Gets a pointer to an [IInstallReferenceEnum](iinstallreferenceenum-interface.md) instance that represents a list of an application's references to the specified assembly.</span></span>  
  
 [<span data-ttu-id="d0d3c-123">GetAppIdAuthority 함수</span><span class="sxs-lookup"><span data-stu-id="d0d3c-123">GetAppIdAuthority Function</span></span>](getappidauthority-function.md)  
 <span data-ttu-id="d0d3c-124">응용 프로그램 id 및 참조에 대 한 키를 관리 하는 [Iappidauthority](iappidauthority-interface.md) 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d0d3c-124">Gets a pointer to an [IAppIdAuthority](iappidauthority-interface.md) instance that manages keys for application identities and references.</span></span>  
  
 [<span data-ttu-id="d0d3c-125">GetAssemblyIdentityFromFile 함수</span><span class="sxs-lookup"><span data-stu-id="d0d3c-125">GetAssemblyIdentityFromFile Function</span></span>](getassemblyidentityfromfile-function.md)  
 <span data-ttu-id="d0d3c-126">`IUnknown`어셈블리에서 지정 된 파일 경로의 지정 된을 사용 하 여 개체에 대 한 포인터를 가져옵니다 `IID` .</span><span class="sxs-lookup"><span data-stu-id="d0d3c-126">Gets a pointer to an `IUnknown` object with the specified `IID` in the assembly at the specified file path.</span></span>  
  
 [<span data-ttu-id="d0d3c-127">GetCachePath 함수</span><span class="sxs-lookup"><span data-stu-id="d0d3c-127">GetCachePath Function</span></span>](getcachepath-function.md)  
 <span data-ttu-id="d0d3c-128">지정 된 플래그를 사용 하 여 캐시 된 어셈블리에 대 한 경로를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d0d3c-128">Gets the path to the cached assembly, using the specified flags.</span></span>  
  
 [<span data-ttu-id="d0d3c-129">GetHistoryFileDirectory 함수</span><span class="sxs-lookup"><span data-stu-id="d0d3c-129">GetHistoryFileDirectory Function</span></span>](gethistoryfiledirectory-function.md)  
 <span data-ttu-id="d0d3c-130">응용 프로그램 기록 디렉터리의 경로를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0d3c-130">Retrieves the path of the application history directory.</span></span>  
  
 [<span data-ttu-id="d0d3c-131">GetIdentityAuthority 함수</span><span class="sxs-lookup"><span data-stu-id="d0d3c-131">GetIdentityAuthority Function</span></span>](getidentityauthority-function.md)  
 <span data-ttu-id="d0d3c-132">코드 개체에 대 한 키를 관리 하는 [IIdentityAuthority](iidentityauthority-interface.md) 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d0d3c-132">Gets a pointer to an [IIdentityAuthority](iidentityauthority-interface.md) instance that manages keys for code objects.</span></span>  
  
 [<span data-ttu-id="d0d3c-133">IsFrameworkAssembly 함수</span><span class="sxs-lookup"><span data-stu-id="d0d3c-133">IsFrameworkAssembly Function</span></span>](isframeworkassembly-function.md)  
 <span data-ttu-id="d0d3c-134">지정 된 어셈블리가 관리 되는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d0d3c-134">Gets a value that indicates whether the specified assembly is managed.</span></span>  
  
 [<span data-ttu-id="d0d3c-135">NukeDownloadedCache 함수</span><span class="sxs-lookup"><span data-stu-id="d0d3c-135">NukeDownloadedCache Function</span></span>](nukedownloadedcache-function.md)  
 <span data-ttu-id="d0d3c-136">공용 언어 런타임 다운로드 캐시를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0d3c-136">Deletes the common language runtime download cache.</span></span>  
  
 [<span data-ttu-id="d0d3c-137">PreBindAssemblyEx 함수</span><span class="sxs-lookup"><span data-stu-id="d0d3c-137">PreBindAssemblyEx Function</span></span>](prebindassemblyex-function.md)  
 <span data-ttu-id="d0d3c-138">어셈블리의 정책 후 표시 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d0d3c-138">Gets the post-policy display name for an assembly.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d0d3c-139">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="d0d3c-139">Related Sections</span></span>  

 [<span data-ttu-id="d0d3c-140">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d0d3c-140">Fusion Interfaces</span></span>](fusion-interfaces.md)  
  
 [<span data-ttu-id="d0d3c-141">Fusion 열거형</span><span class="sxs-lookup"><span data-stu-id="d0d3c-141">Fusion Enumerations</span></span>](fusion-enumerations.md)  
  
 [<span data-ttu-id="d0d3c-142">Fusion 구조체</span><span class="sxs-lookup"><span data-stu-id="d0d3c-142">Fusion Structures</span></span>](fusion-structures.md)  
  
 [<span data-ttu-id="d0d3c-143">전역 어셈블리 캐시</span><span class="sxs-lookup"><span data-stu-id="d0d3c-143">Global Assembly Cache</span></span>](../../app-domains/gac.md)
