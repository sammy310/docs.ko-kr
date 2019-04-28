---
title: Fusion 인터페이스
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework fusion]
- fusion interfaces [.NET Framework]
- unmanaged interfaces [.NET Framework], fusion
ms.assetid: e2cf98b7-40c1-4f74-86c7-8a76dd9da677
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ec2fd3b309820f2bfb7f6091cc3db720db497408
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697669"
---
# <a name="fusion-interfaces"></a><span data-ttu-id="52a1f-102">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="52a1f-102">Fusion Interfaces</span></span>
<span data-ttu-id="52a1f-103">이 섹션에서는 응용 프로그램 리소스의 속성에 액세스 하는 데 응용 프로그램에 대 한 해당 리소스의 정확한 버전을 찾을 fusion API를 사용 하는 관리 되지 않는 인터페이스를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="52a1f-103">This section describes the unmanaged interfaces that the fusion API uses to access the properties of an application's resources and to locate the correct versions of those resources for the application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="52a1f-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="52a1f-104">In This Section</span></span>  
 [<span data-ttu-id="52a1f-105">IAppIdAuthority 인터페이스</span><span class="sxs-lookup"><span data-stu-id="52a1f-105">IAppIdAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md)  
 <span data-ttu-id="52a1f-106">생성 하 고 응용 프로그램 id 및 참조에 대 한 키를 비교 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="52a1f-106">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
 [<span data-ttu-id="52a1f-107">IAssemblyCache 인터페이스</span><span class="sxs-lookup"><span data-stu-id="52a1f-107">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)  
 <span data-ttu-id="52a1f-108">전역 어셈블리 캐시의 표현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="52a1f-108">Provides a representation of the global assembly cache.</span></span>  
  
 [<span data-ttu-id="52a1f-109">IAssemblyCacheItem 인터페이스</span><span class="sxs-lookup"><span data-stu-id="52a1f-109">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)  
 <span data-ttu-id="52a1f-110">전역 어셈블리 캐시에서 단일 어셈블리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="52a1f-110">Represents a single assembly in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="52a1f-111">IAssemblyEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="52a1f-111">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)  
 <span data-ttu-id="52a1f-112">배열에 대 한 열거자를 나타내는 `IAssemblyName` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="52a1f-112">Represents an enumerator for an array of `IAssemblyName` objects.</span></span>  
  
 [<span data-ttu-id="52a1f-113">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="52a1f-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 <span data-ttu-id="52a1f-114">설명 하 고 어셈블리의 고유 id를 사용 하 여 작업에 대 한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="52a1f-114">Provides methods for describing and working with an assembly's unique identity.</span></span>  
  
 [<span data-ttu-id="52a1f-115">IDefinitionAppId 인터페이스</span><span class="sxs-lookup"><span data-stu-id="52a1f-115">IDefinitionAppId Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md)  
 <span data-ttu-id="52a1f-116">현재 범위에서 응용 프로그램을 정의 하는 코드에 대 한 고유 식별자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="52a1f-116">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
 [<span data-ttu-id="52a1f-117">IDefinitionIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="52a1f-117">IDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)  
 <span data-ttu-id="52a1f-118">현재 범위에서 응용 프로그램을 정의 하는 코드의 고유한 시그니처를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="52a1f-118">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
 [<span data-ttu-id="52a1f-119">IEnumDefinitionIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="52a1f-119">IEnumDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md)  
 <span data-ttu-id="52a1f-120">컬렉션의 열거자 역할을 `IDefinitionIdentity` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="52a1f-120">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
 [<span data-ttu-id="52a1f-121">IEnumIDENTITY_ATTRIBUTE 인터페이스</span><span class="sxs-lookup"><span data-stu-id="52a1f-121">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)  
 <span data-ttu-id="52a1f-122">현재 범위에 있는 코드 개체의 특성에 대 한 열거자를 역할도합니다.</span><span class="sxs-lookup"><span data-stu-id="52a1f-122">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
 [<span data-ttu-id="52a1f-123">IEnumReferenceIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="52a1f-123">IEnumReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumreferenceidentity-interface.md)  
 <span data-ttu-id="52a1f-124">컬렉션의 열거자 역할을 `IReferenceIdentity` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="52a1f-124">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
 [<span data-ttu-id="52a1f-125">IIdentityAuthority 인터페이스</span><span class="sxs-lookup"><span data-stu-id="52a1f-125">IIdentityAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md)  
 <span data-ttu-id="52a1f-126">코드 개체에 대 한 id 키를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="52a1f-126">Manages identity keys for code objects.</span></span>  
  
 [<span data-ttu-id="52a1f-127">IInstallReferenceEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="52a1f-127">IInstallReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)  
 <span data-ttu-id="52a1f-128">참조 된 어셈블리가 전역 어셈블리 캐시에 설치에 대 한 열거자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="52a1f-128">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="52a1f-129">IInstallReferenceItem 인터페이스</span><span class="sxs-lookup"><span data-stu-id="52a1f-129">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)  
 <span data-ttu-id="52a1f-130">전역 어셈블리 캐시에 설치 된 항목을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="52a1f-130">Represents an item installed in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="52a1f-131">IReferenceAppId 인터페이스</span><span class="sxs-lookup"><span data-stu-id="52a1f-131">IReferenceAppId Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md)  
 <span data-ttu-id="52a1f-132">현재 범위에서 응용 프로그램에 대 한 고유 식별자에 대 한 참조를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="52a1f-132">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
 [<span data-ttu-id="52a1f-133">IReferenceIdentity 인터페이스</span><span class="sxs-lookup"><span data-stu-id="52a1f-133">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)  
 <span data-ttu-id="52a1f-134">코드 개체의 고유 서명에 대 한 참조를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="52a1f-134">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="52a1f-135">참조</span><span class="sxs-lookup"><span data-stu-id="52a1f-135">Reference</span></span>  
 <xref:System.Reflection>  
  
 <xref:System.Reflection.Emit>  
  
## <a name="related-sections"></a><span data-ttu-id="52a1f-136">관련 단원</span><span class="sxs-lookup"><span data-stu-id="52a1f-136">Related Sections</span></span>  
 [<span data-ttu-id="52a1f-137">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="52a1f-137">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)  
  
 [<span data-ttu-id="52a1f-138">Fusion 열거형</span><span class="sxs-lookup"><span data-stu-id="52a1f-138">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)  
  
 [<span data-ttu-id="52a1f-139">Fusion 구조체</span><span class="sxs-lookup"><span data-stu-id="52a1f-139">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
