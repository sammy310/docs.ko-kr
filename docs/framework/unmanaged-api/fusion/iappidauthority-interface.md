---
title: IAppIdAuthority 인터페이스
ms.date: 03/30/2017
api_name:
- IAppIdAuthority
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAppIdAuthority
helpviewer_keywords:
- IAppIdAuthority interface [.NET Framework fusion]
ms.assetid: ec354fa1-1efd-41b0-bc43-b90597b6e253
topic_type:
- apiref
ms.openlocfilehash: a344f2ab5d9a7aa92018c47ee7a162cd1721aeb5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732114"
---
# <a name="iappidauthority-interface"></a><span data-ttu-id="f8134-102">IAppIdAuthority 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f8134-102">IAppIdAuthority Interface</span></span>

<span data-ttu-id="f8134-103">응용 프로그램 id 및 참조에 대 한 키를 생성 하 고 비교 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8134-103">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f8134-104">메서드</span><span class="sxs-lookup"><span data-stu-id="f8134-104">Methods</span></span>  
  
|<span data-ttu-id="f8134-105">메서드</span><span class="sxs-lookup"><span data-stu-id="f8134-105">Method</span></span>|<span data-ttu-id="f8134-106">설명</span><span class="sxs-lookup"><span data-stu-id="f8134-106">Description</span></span>|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|<span data-ttu-id="f8134-107">지정 된 두 [Idefinitionappid](idefinitionappid-interface.md) 인스턴스가 같은지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f8134-107">Gets a value that indicates whether the two specified [IDefinitionAppId](idefinitionappid-interface.md) instances are equal.</span></span> <span data-ttu-id="f8134-108">IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION 플래그 값을 전달 하 여 해당 버전 정보를 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8134-108">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreReferencesEqual`|<span data-ttu-id="f8134-109">지정 된 두 [Ireferenceappid](ireferenceappid-interface.md) 인스턴스가 같은지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f8134-109">Gets a value that indicates whether the two specified [IReferenceAppId](ireferenceappid-interface.md) instances are equal.</span></span> <span data-ttu-id="f8134-110">IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION 플래그 값을 전달 하 여 해당 버전 정보를 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8134-110">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="f8134-111">지정 된 두 문자열 정의가 같은지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f8134-111">Gets a value that indicates whether the two specified string definitions are equal.</span></span> <span data-ttu-id="f8134-112">IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION 플래그 값을 전달 하 여 해당 버전 정보를 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8134-112">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualReferencesEqual`|<span data-ttu-id="f8134-113">지정 된 두 문자열 참조가 같은지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f8134-113">Gets a value that indicates whether the two specified string references are equal.</span></span> <span data-ttu-id="f8134-114">IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION 플래그 값을 전달 하 여 해당 버전 정보를 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8134-114">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::CreateDefinition`|<span data-ttu-id="f8134-115">`IDefinitionAppId`현재 범위에서 어셈블리를 나타내는 새로 생성 된 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f8134-115">Gets an interface pointer to a newly generated `IDefinitionAppId` instance that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::CreateReference`|<span data-ttu-id="f8134-116">`IReferenceAppId`현재 범위에서 어셈블리를 나타내는 새로 만든에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f8134-116">Gets an interface pointer to a newly created `IReferenceAppId` that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::DefinitionToText`|<span data-ttu-id="f8134-117">지정 된 `IDefinitionAppId` 플래그 값을 사용 하 여 지정 된의 문자열 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f8134-117">Gets a string version of the specified `IDefinitionAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="f8134-118">지정 된와가 같은 어셈블리를 나타내는지 여부를 나타내는 값을 가져옵니다 `IDefinitionAppId` `IReferenceAppId` .</span><span class="sxs-lookup"><span data-stu-id="f8134-118">Gets a value that indicates whether the specified `IDefinitionAppId` and `IReferenceAppId` represent the same assembly.</span></span>|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="f8134-119">지정 된 정의 문자열과 참조 문자열이 동일한 어셈블리를 나타내는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f8134-119">Gets a value that indicates whether the specified definition string and reference string represent the same assembly.</span></span>|  
|`IAppIdAuthority::GenerateDefinitionKey`|<span data-ttu-id="f8134-120">지정 된 인스턴스를 나타내는 문자열 키를 가져옵니다 `IDefinitionAppId` .</span><span class="sxs-lookup"><span data-stu-id="f8134-120">Gets a string key that represents the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::GenerateReferenceKey`|<span data-ttu-id="f8134-121">지정 된 인스턴스를 나타내는 문자열 키를 가져옵니다 `IReferenceAppId` .</span><span class="sxs-lookup"><span data-stu-id="f8134-121">Gets a string key that represents the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::HashDefinition`|<span data-ttu-id="f8134-122">지정 된 인스턴스에 대 한 해시 키를 가져옵니다 `IDefinitionAppId` .</span><span class="sxs-lookup"><span data-stu-id="f8134-122">Gets a hash key for the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::HashReference`|<span data-ttu-id="f8134-123">지정 된 인스턴스에 대 한 해시 키를 가져옵니다 `IReferenceAppId` .</span><span class="sxs-lookup"><span data-stu-id="f8134-123">Gets a hash key for the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::ReferenceToText`|<span data-ttu-id="f8134-124">지정 된 `IReferenceAppId` 플래그 값을 사용 하 여 지정 된의 문자열 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f8134-124">Gets a string version of the specified `IReferenceAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::TextToDefinition`|<span data-ttu-id="f8134-125">`IDefinitionAppId`지정 된 문자열 키가 참조 하는 어셈블리를 나타내는 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f8134-125">Gets an interface pointer to an `IDefinitionAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
|`IAppIdAuthority::TextToReference`|<span data-ttu-id="f8134-126">`IReferenceAppId`지정 된 문자열 키가 참조 하는 어셈블리를 나타내는 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f8134-126">Gets an interface pointer to an `IReferenceAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f8134-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f8134-127">Requirements</span></span>  

 <span data-ttu-id="f8134-128">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8134-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8134-129">**헤더:** 격리. h</span><span class="sxs-lookup"><span data-stu-id="f8134-129">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="f8134-130">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8134-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8134-131">참조</span><span class="sxs-lookup"><span data-stu-id="f8134-131">See also</span></span>

- [<span data-ttu-id="f8134-132">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f8134-132">Fusion Interfaces</span></span>](fusion-interfaces.md)
