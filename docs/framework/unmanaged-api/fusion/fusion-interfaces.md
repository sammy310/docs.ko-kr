---
description: '다음에 대 한 자세한 정보: Fusion 인터페이스'
title: Fusion 인터페이스
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework fusion]
- fusion interfaces [.NET Framework]
- unmanaged interfaces [.NET Framework], fusion
ms.assetid: e2cf98b7-40c1-4f74-86c7-8a76dd9da677
ms.openlocfilehash: 3b6ca64b40ebc1a7b38129d897059ca628d3914c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761067"
---
# <a name="fusion-interfaces"></a><span data-ttu-id="93922-103">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="93922-103">Fusion Interfaces</span></span>

<span data-ttu-id="93922-104">이 섹션에서는 fusion API에서 응용 프로그램 리소스의 속성에 액세스 하 고 응용 프로그램에 대해 해당 리소스의 올바른 버전을 찾는 데 사용 하는 관리 되지 않는 인터페이스에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="93922-104">This section describes the unmanaged interfaces that the fusion API uses to access the properties of an application's resources and to locate the correct versions of those resources for the application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="93922-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="93922-105">In This Section</span></span>  

 [<span data-ttu-id="93922-106">IAppIdAuthority 인터페이스</span><span class="sxs-lookup"><span data-stu-id="93922-106">IAppIdAuthority Interface</span></span>](iappidauthority-interface.md)  
 <span data-ttu-id="93922-107">응용 프로그램 id 및 참조에 대 한 키를 생성 하 고 비교 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="93922-107">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
 [<span data-ttu-id="93922-108">IAssemblyCache 인터페이스</span><span class="sxs-lookup"><span data-stu-id="93922-108">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)  
 <span data-ttu-id="93922-109">전역 어셈블리 캐시의 표현을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="93922-109">Provides a representation of the global assembly cache.</span></span>  
  
 [<span data-ttu-id="93922-110">IAssemblyCacheItem 인터페이스</span><span class="sxs-lookup"><span data-stu-id="93922-110">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)  
 <span data-ttu-id="93922-111">전역 어셈블리 캐시의 단일 어셈블리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="93922-111">Represents a single assembly in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="93922-112">IAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="93922-112">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)  
 <span data-ttu-id="93922-113">개체의 배열에 대 한 열거자를 나타냅니다 `IAssemblyName` .</span><span class="sxs-lookup"><span data-stu-id="93922-113">Represents an enumerator for an array of `IAssemblyName` objects.</span></span>  
  
 [<span data-ttu-id="93922-114">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="93922-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)  
 <span data-ttu-id="93922-115">어셈블리의 고유 id를 설명 하 고 작업 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="93922-115">Provides methods for describing and working with an assembly's unique identity.</span></span>  
  
 [<span data-ttu-id="93922-116">IDefinitionAppId 인터페이스</span><span class="sxs-lookup"><span data-stu-id="93922-116">IDefinitionAppId Interface</span></span>](idefinitionappid-interface.md)  
 <span data-ttu-id="93922-117">현재 범위에서 응용 프로그램을 정의 하는 코드의 고유 식별자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="93922-117">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
 [<span data-ttu-id="93922-118">IDefinitionIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="93922-118">IDefinitionIdentity Interface</span></span>](idefinitionidentity-interface.md)  
 <span data-ttu-id="93922-119">현재 범위에서 응용 프로그램을 정의 하는 코드의 고유 서명을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="93922-119">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
 [<span data-ttu-id="93922-120">IEnumDefinitionIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="93922-120">IEnumDefinitionIdentity Interface</span></span>](ienumdefinitionidentity-interface.md)  
 <span data-ttu-id="93922-121">개체의 컬렉션에 대 한 열거자 역할을 `IDefinitionIdentity` 합니다.</span><span class="sxs-lookup"><span data-stu-id="93922-121">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
 [<span data-ttu-id="93922-122">IEnumIDENTITY_ATTRIBUTE 인터페이스</span><span class="sxs-lookup"><span data-stu-id="93922-122">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](ienumidentity-attribute-interface.md)  
 <span data-ttu-id="93922-123">현재 범위에 있는 코드 개체의 특성에 대 한 열거자 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="93922-123">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
 [<span data-ttu-id="93922-124">IEnumReferenceIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="93922-124">IEnumReferenceIdentity Interface</span></span>](ienumreferenceidentity-interface.md)  
 <span data-ttu-id="93922-125">개체의 컬렉션에 대 한 열거자 역할을 `IReferenceIdentity` 합니다.</span><span class="sxs-lookup"><span data-stu-id="93922-125">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
 [<span data-ttu-id="93922-126">IIdentityAuthority 인터페이스</span><span class="sxs-lookup"><span data-stu-id="93922-126">IIdentityAuthority Interface</span></span>](iidentityauthority-interface.md)  
 <span data-ttu-id="93922-127">코드 개체에 대 한 id 키를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="93922-127">Manages identity keys for code objects.</span></span>  
  
 [<span data-ttu-id="93922-128">IInstallReferenceEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="93922-128">IInstallReferenceEnum Interface</span></span>](iinstallreferenceenum-interface.md)  
 <span data-ttu-id="93922-129">전역 어셈블리 캐시에 설치 된 참조 된 어셈블리의 열거자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="93922-129">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="93922-130">IInstallReferenceItem 인터페이스</span><span class="sxs-lookup"><span data-stu-id="93922-130">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)  
 <span data-ttu-id="93922-131">전역 어셈블리 캐시에 설치 된 항목을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="93922-131">Represents an item installed in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="93922-132">IReferenceAppId 인터페이스</span><span class="sxs-lookup"><span data-stu-id="93922-132">IReferenceAppId Interface</span></span>](ireferenceappid-interface.md)  
 <span data-ttu-id="93922-133">현재 범위의 응용 프로그램에 대 한 고유 식별자에 대 한 참조를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="93922-133">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
 [<span data-ttu-id="93922-134">IReferenceIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="93922-134">IReferenceIdentity Interface</span></span>](ireferenceidentity-interface.md)  
 <span data-ttu-id="93922-135">코드 개체의 고유 서명에 대 한 참조를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="93922-135">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="93922-136">참고</span><span class="sxs-lookup"><span data-stu-id="93922-136">Reference</span></span>  

 <xref:System.Reflection>  
  
 <xref:System.Reflection.Emit>  
  
## <a name="related-sections"></a><span data-ttu-id="93922-137">관련 단원</span><span class="sxs-lookup"><span data-stu-id="93922-137">Related Sections</span></span>  

 [<span data-ttu-id="93922-138">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="93922-138">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)  
  
 [<span data-ttu-id="93922-139">Fusion 열거형</span><span class="sxs-lookup"><span data-stu-id="93922-139">Fusion Enumerations</span></span>](fusion-enumerations.md)  
  
 [<span data-ttu-id="93922-140">Fusion 구조체</span><span class="sxs-lookup"><span data-stu-id="93922-140">Fusion Structures</span></span>](fusion-structures.md)
