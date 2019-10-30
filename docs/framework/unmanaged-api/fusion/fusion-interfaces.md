---
title: Fusion 인터페이스
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework fusion]
- fusion interfaces [.NET Framework]
- unmanaged interfaces [.NET Framework], fusion
ms.assetid: e2cf98b7-40c1-4f74-86c7-8a76dd9da677
ms.openlocfilehash: 81c66825e69d9526abddfe06133426a2274ad08f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108190"
---
# <a name="fusion-interfaces"></a><span data-ttu-id="be8d8-102">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="be8d8-102">Fusion Interfaces</span></span>
<span data-ttu-id="be8d8-103">이 섹션에서는 fusion API에서 응용 프로그램 리소스의 속성에 액세스 하 고 응용 프로그램에 대해 해당 리소스의 올바른 버전을 찾는 데 사용 하는 관리 되지 않는 인터페이스에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="be8d8-103">This section describes the unmanaged interfaces that the fusion API uses to access the properties of an application's resources and to locate the correct versions of those resources for the application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="be8d8-104">단원 내용</span><span class="sxs-lookup"><span data-stu-id="be8d8-104">In This Section</span></span>  
 [<span data-ttu-id="be8d8-105">IAppIdAuthority 인터페이스</span><span class="sxs-lookup"><span data-stu-id="be8d8-105">IAppIdAuthority Interface</span></span>](iappidauthority-interface.md)  
 <span data-ttu-id="be8d8-106">응용 프로그램 id 및 참조에 대 한 키를 생성 하 고 비교 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="be8d8-106">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
 [<span data-ttu-id="be8d8-107">IAssemblyCache 인터페이스</span><span class="sxs-lookup"><span data-stu-id="be8d8-107">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)  
 <span data-ttu-id="be8d8-108">전역 어셈블리 캐시의 표현을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="be8d8-108">Provides a representation of the global assembly cache.</span></span>  
  
 [<span data-ttu-id="be8d8-109">IAssemblyCacheItem 인터페이스</span><span class="sxs-lookup"><span data-stu-id="be8d8-109">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)  
 <span data-ttu-id="be8d8-110">전역 어셈블리 캐시의 단일 어셈블리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="be8d8-110">Represents a single assembly in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="be8d8-111">IAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="be8d8-111">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)  
 <span data-ttu-id="be8d8-112">`IAssemblyName` 개체의 배열에 대 한 열거자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="be8d8-112">Represents an enumerator for an array of `IAssemblyName` objects.</span></span>  
  
 [<span data-ttu-id="be8d8-113">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="be8d8-113">IAssemblyName Interface</span></span>](iassemblyname-interface.md)  
 <span data-ttu-id="be8d8-114">어셈블리의 고유 id를 설명 하 고 작업 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="be8d8-114">Provides methods for describing and working with an assembly's unique identity.</span></span>  
  
 [<span data-ttu-id="be8d8-115">IDefinitionAppId 인터페이스</span><span class="sxs-lookup"><span data-stu-id="be8d8-115">IDefinitionAppId Interface</span></span>](idefinitionappid-interface.md)  
 <span data-ttu-id="be8d8-116">현재 범위에서 응용 프로그램을 정의 하는 코드의 고유 식별자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="be8d8-116">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
 [<span data-ttu-id="be8d8-117">IDefinitionIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="be8d8-117">IDefinitionIdentity Interface</span></span>](idefinitionidentity-interface.md)  
 <span data-ttu-id="be8d8-118">현재 범위에서 응용 프로그램을 정의 하는 코드의 고유 서명을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="be8d8-118">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
 [<span data-ttu-id="be8d8-119">IEnumDefinitionIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="be8d8-119">IEnumDefinitionIdentity Interface</span></span>](ienumdefinitionidentity-interface.md)  
 <span data-ttu-id="be8d8-120">`IDefinitionIdentity` 개체의 컬렉션에 대 한 열거자 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="be8d8-120">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
 [<span data-ttu-id="be8d8-121">IEnumIDENTITY_ATTRIBUTE 인터페이스</span><span class="sxs-lookup"><span data-stu-id="be8d8-121">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](ienumidentity-attribute-interface.md)  
 <span data-ttu-id="be8d8-122">현재 범위에 있는 코드 개체의 특성에 대 한 열거자 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="be8d8-122">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
 [<span data-ttu-id="be8d8-123">IEnumReferenceIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="be8d8-123">IEnumReferenceIdentity Interface</span></span>](ienumreferenceidentity-interface.md)  
 <span data-ttu-id="be8d8-124">`IReferenceIdentity` 개체의 컬렉션에 대 한 열거자 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="be8d8-124">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
 [<span data-ttu-id="be8d8-125">IIdentityAuthority 인터페이스</span><span class="sxs-lookup"><span data-stu-id="be8d8-125">IIdentityAuthority Interface</span></span>](iidentityauthority-interface.md)  
 <span data-ttu-id="be8d8-126">코드 개체에 대 한 id 키를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="be8d8-126">Manages identity keys for code objects.</span></span>  
  
 [<span data-ttu-id="be8d8-127">IInstallReferenceEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="be8d8-127">IInstallReferenceEnum Interface</span></span>](iinstallreferenceenum-interface.md)  
 <span data-ttu-id="be8d8-128">전역 어셈블리 캐시에 설치 된 참조 된 어셈블리의 열거자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="be8d8-128">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="be8d8-129">IInstallReferenceItem 인터페이스</span><span class="sxs-lookup"><span data-stu-id="be8d8-129">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)  
 <span data-ttu-id="be8d8-130">전역 어셈블리 캐시에 설치 된 항목을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="be8d8-130">Represents an item installed in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="be8d8-131">IReferenceAppId 인터페이스</span><span class="sxs-lookup"><span data-stu-id="be8d8-131">IReferenceAppId Interface</span></span>](ireferenceappid-interface.md)  
 <span data-ttu-id="be8d8-132">현재 범위의 응용 프로그램에 대 한 고유 식별자에 대 한 참조를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="be8d8-132">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
 [<span data-ttu-id="be8d8-133">IReferenceIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="be8d8-133">IReferenceIdentity Interface</span></span>](ireferenceidentity-interface.md)  
 <span data-ttu-id="be8d8-134">코드 개체의 고유 서명에 대 한 참조를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="be8d8-134">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="be8d8-135">참고</span><span class="sxs-lookup"><span data-stu-id="be8d8-135">Reference</span></span>  
 <xref:System.Reflection>  
  
 <xref:System.Reflection.Emit>  
  
## <a name="related-sections"></a><span data-ttu-id="be8d8-136">관련 단원</span><span class="sxs-lookup"><span data-stu-id="be8d8-136">Related Sections</span></span>  
 [<span data-ttu-id="be8d8-137">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="be8d8-137">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)  
  
 [<span data-ttu-id="be8d8-138">Fusion 열거형</span><span class="sxs-lookup"><span data-stu-id="be8d8-138">Fusion Enumerations</span></span>](fusion-enumerations.md)  
  
 [<span data-ttu-id="be8d8-139">Fusion 구조체</span><span class="sxs-lookup"><span data-stu-id="be8d8-139">Fusion Structures</span></span>](fusion-structures.md)
