---
title: IIdentityAuthority 인터페이스
ms.date: 03/30/2017
api_name:
- IIdentityAuthority
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IIdentityAuthority
helpviewer_keywords:
- IIdentityAuthority interface [.NET Framework fusion]
ms.assetid: 6277f914-51a8-49be-bec6-52d6d648527d
topic_type:
- apiref
ms.openlocfilehash: 3e2d2335e37ced9139ea44092f10b19566894681
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127086"
---
# <a name="iidentityauthority-interface"></a><span data-ttu-id="347a8-102">IIdentityAuthority 인터페이스</span><span class="sxs-lookup"><span data-stu-id="347a8-102">IIdentityAuthority Interface</span></span>

<span data-ttu-id="347a8-103">코드 개체에 대 한 id 키를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="347a8-103">Manages identity keys for code objects.</span></span>

## <a name="methods"></a><span data-ttu-id="347a8-104">메서드</span><span class="sxs-lookup"><span data-stu-id="347a8-104">Methods</span></span>

|<span data-ttu-id="347a8-105">메서드</span><span class="sxs-lookup"><span data-stu-id="347a8-105">Method</span></span>|<span data-ttu-id="347a8-106">설명</span><span class="sxs-lookup"><span data-stu-id="347a8-106">Description</span></span>|
|------------|-----------------|
|`IIdentityAuthority::AreDefinitionsEqual`|<span data-ttu-id="347a8-107">지정 된 두 [Idefinitionidentity](idefinitionidentity-interface.md) 인스턴스가 같은지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="347a8-107">Gets a value that indicates whether the two specified [IDefinitionIdentity](idefinitionidentity-interface.md) instances are equal.</span></span>|
|`IIdentityAuthority::AreReferencesEqual`|<span data-ttu-id="347a8-108">지정 된 두 [IReferenceIdentity](ireferenceidentity-interface.md) 인스턴스가 같은지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="347a8-108">Gets a value that indicates whether the two specified [IReferenceIdentity](ireferenceidentity-interface.md) instances are equal.</span></span>|
|`IIdentityAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="347a8-109">지정 된 두 문자열 정의 id 표현이 같은지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="347a8-109">Gets a value that indicates whether the two specified string definition identity representations are equal.</span></span>|
|`IIdentityAuthority::AreTextualReferencesEqual`|<span data-ttu-id="347a8-110">지정 된 두 문자열 참조 id 표현이 같은지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="347a8-110">Gets a value that indicates whether the two specified string reference identity representations are equal.</span></span>|
|`IIdentityAuthority::CreateDefinition`|<span data-ttu-id="347a8-111">현재 범위에 있는 코드 개체를 나타내는 새 `IDefinitionIdentity` 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="347a8-111">Gets a pointer to a new `IDefinitionIdentity` instance that represents the code object in the current scope.</span></span>|
|`IIdentityAuthority::CreateReference`|<span data-ttu-id="347a8-112">현재 범위에 있는 코드 개체를 나타내는 새 `IReferenceIdentity` 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="347a8-112">Gets a pointer to a new `IReferenceIdentity` instance that represents the code object in the current scope.</span></span>|
|`IIdentityAuthority::DefinitionToText`|<span data-ttu-id="347a8-113">지정 된 `IDefinitionIdentity`의 형식이 지정 된 문자열 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="347a8-113">Gets a formatted string version of the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::DefinitionToTextBuffer`|<span data-ttu-id="347a8-114">지정 된 와이드 문자 버퍼를 지정 된 `IDefinitionIdentity`의 문자열 버전으로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="347a8-114">Fills the specified wide character buffer with a string version of the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="347a8-115">지정 된 `IDefinitionIdentity`와 `IReferenceIdentity` 인스턴스가 동일한 코드 개체를 참조 하는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="347a8-115">Gets a value that indicates whether the specified `IDefinitionIdentity` and `IReferenceIdentity` instances refer to the same code object.</span></span>|
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="347a8-116">지정 된 문자열이 동일한 코드 개체를 참조 하는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="347a8-116">Gets a value that indicates whether the specified strings refer to the same code object.</span></span>|
|`IIdentityAuthority::GenerateDefinitionKey`|<span data-ttu-id="347a8-117">지정 된 `IDefinitionIdentity`에 대해 새로 만든 문자열 키에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="347a8-117">Gets a pointer to a newly created string key for the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::GenerateReferenceKey`|<span data-ttu-id="347a8-118">지정 된 `IReferenceIdentity`에 대해 새로 만든 문자열 키에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="347a8-118">Gets a pointer to a newly created string key for the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::HashDefinition`|<span data-ttu-id="347a8-119">지정 된 `IDefinitionIdentity`에 대 한 해시 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="347a8-119">Gets a hash value for the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::HashReference`|<span data-ttu-id="347a8-120">지정 된 `IReferenceIdentity`에 대 한 해시 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="347a8-120">Gets a hash value for the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::ReferenceToText`|<span data-ttu-id="347a8-121">지정 된 `IReferenceIdentity`의 형식이 지정 된 문자열 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="347a8-121">Gets a formatted string version of the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::ReferenceToTextBuffer`|<span data-ttu-id="347a8-122">지정 된 와이드 문자 버퍼를 지정 된 `IReferenceIdentity`의 문자열 버전으로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="347a8-122">Fills the specified wide character buffer with a string version of the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::TextToDefinition`|<span data-ttu-id="347a8-123">지정 된 형식이 지정 된 문자열에서 생성 된 `IDefinitionIdentity` 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="347a8-123">Gets an interface pointer to an `IDefinitionIdentity` instance generated from the specified formatted string.</span></span>|
|`IIdentityAuthority::TextToReference`|<span data-ttu-id="347a8-124">지정 된 형식이 지정 된 문자열에서 생성 된 `IReferenceIdentity` 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="347a8-124">Gets an interface pointer to an `IReferenceIdentity` instance generated from the specified formatted string.</span></span>|

## <a name="requirements"></a><span data-ttu-id="347a8-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="347a8-125">Requirements</span></span>

<span data-ttu-id="347a8-126">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="347a8-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="347a8-127">**헤더:** 격리. h</span><span class="sxs-lookup"><span data-stu-id="347a8-127">**Header:** Isolation.h</span></span>

<span data-ttu-id="347a8-128">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="347a8-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="347a8-129">참조</span><span class="sxs-lookup"><span data-stu-id="347a8-129">See also</span></span>

- [<span data-ttu-id="347a8-130">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="347a8-130">Fusion Interfaces</span></span>](fusion-interfaces.md)
