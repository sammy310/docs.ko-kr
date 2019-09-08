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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7421e0d0e1a1f0e1a5fbe0d0eb7d5a0ab2a48b9a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796426"
---
# <a name="iidentityauthority-interface"></a><span data-ttu-id="13fcd-102">IIdentityAuthority 인터페이스</span><span class="sxs-lookup"><span data-stu-id="13fcd-102">IIdentityAuthority Interface</span></span>

<span data-ttu-id="13fcd-103">코드 개체에 대 한 id 키를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="13fcd-103">Manages identity keys for code objects.</span></span>

## <a name="methods"></a><span data-ttu-id="13fcd-104">메서드</span><span class="sxs-lookup"><span data-stu-id="13fcd-104">Methods</span></span>

|<span data-ttu-id="13fcd-105">메서드</span><span class="sxs-lookup"><span data-stu-id="13fcd-105">Method</span></span>|<span data-ttu-id="13fcd-106">설명</span><span class="sxs-lookup"><span data-stu-id="13fcd-106">Description</span></span>|
|------------|-----------------|
|`IIdentityAuthority::AreDefinitionsEqual`|<span data-ttu-id="13fcd-107">지정 된 두 [Idefinitionidentity](idefinitionidentity-interface.md) 인스턴스가 같은지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="13fcd-107">Gets a value that indicates whether the two specified [IDefinitionIdentity](idefinitionidentity-interface.md) instances are equal.</span></span>|
|`IIdentityAuthority::AreReferencesEqual`|<span data-ttu-id="13fcd-108">지정 된 두 [IReferenceIdentity](ireferenceidentity-interface.md) 인스턴스가 같은지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="13fcd-108">Gets a value that indicates whether the two specified [IReferenceIdentity](ireferenceidentity-interface.md) instances are equal.</span></span>|
|`IIdentityAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="13fcd-109">지정 된 두 문자열 정의 id 표현이 같은지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="13fcd-109">Gets a value that indicates whether the two specified string definition identity representations are equal.</span></span>|
|`IIdentityAuthority::AreTextualReferencesEqual`|<span data-ttu-id="13fcd-110">지정 된 두 문자열 참조 id 표현이 같은지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="13fcd-110">Gets a value that indicates whether the two specified string reference identity representations are equal.</span></span>|
|`IIdentityAuthority::CreateDefinition`|<span data-ttu-id="13fcd-111">현재 범위에 있는 코드 개체 `IDefinitionIdentity` 를 나타내는 새 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="13fcd-111">Gets a pointer to a new `IDefinitionIdentity` instance that represents the code object in the current scope.</span></span>|
|`IIdentityAuthority::CreateReference`|<span data-ttu-id="13fcd-112">현재 범위에 있는 코드 개체 `IReferenceIdentity` 를 나타내는 새 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="13fcd-112">Gets a pointer to a new `IReferenceIdentity` instance that represents the code object in the current scope.</span></span>|
|`IIdentityAuthority::DefinitionToText`|<span data-ttu-id="13fcd-113">지정 된의 형식이 지정 `IDefinitionIdentity`된 문자열 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="13fcd-113">Gets a formatted string version of the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::DefinitionToTextBuffer`|<span data-ttu-id="13fcd-114">지정 된 와이드 문자 버퍼를 지정 `IDefinitionIdentity`된의 문자열 버전으로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="13fcd-114">Fills the specified wide character buffer with a string version of the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="13fcd-115">지정 `IDefinitionIdentity` 된 및 `IReferenceIdentity` 인스턴스가 동일한 코드 개체를 참조 하는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="13fcd-115">Gets a value that indicates whether the specified `IDefinitionIdentity` and `IReferenceIdentity` instances refer to the same code object.</span></span>|
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="13fcd-116">지정 된 문자열이 동일한 코드 개체를 참조 하는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="13fcd-116">Gets a value that indicates whether the specified strings refer to the same code object.</span></span>|
|`IIdentityAuthority::GenerateDefinitionKey`|<span data-ttu-id="13fcd-117">지정 `IDefinitionIdentity`된에 대해 새로 만든 문자열 키에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="13fcd-117">Gets a pointer to a newly created string key for the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::GenerateReferenceKey`|<span data-ttu-id="13fcd-118">지정 `IReferenceIdentity`된에 대해 새로 만든 문자열 키에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="13fcd-118">Gets a pointer to a newly created string key for the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::HashDefinition`|<span data-ttu-id="13fcd-119">지정 `IDefinitionIdentity`된에 대 한 해시 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="13fcd-119">Gets a hash value for the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::HashReference`|<span data-ttu-id="13fcd-120">지정 `IReferenceIdentity`된에 대 한 해시 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="13fcd-120">Gets a hash value for the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::ReferenceToText`|<span data-ttu-id="13fcd-121">지정 된의 형식이 지정 `IReferenceIdentity`된 문자열 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="13fcd-121">Gets a formatted string version of the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::ReferenceToTextBuffer`|<span data-ttu-id="13fcd-122">지정 된 와이드 문자 버퍼를 지정 `IReferenceIdentity`된의 문자열 버전으로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="13fcd-122">Fills the specified wide character buffer with a string version of the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::TextToDefinition`|<span data-ttu-id="13fcd-123">지정 된 형식이 지정 된 문자열 `IDefinitionIdentity` 에서 생성 된 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="13fcd-123">Gets an interface pointer to an `IDefinitionIdentity` instance generated from the specified formatted string.</span></span>|
|`IIdentityAuthority::TextToReference`|<span data-ttu-id="13fcd-124">지정 된 형식이 지정 된 문자열 `IReferenceIdentity` 에서 생성 된 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="13fcd-124">Gets an interface pointer to an `IReferenceIdentity` instance generated from the specified formatted string.</span></span>|

## <a name="requirements"></a><span data-ttu-id="13fcd-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="13fcd-125">Requirements</span></span>

<span data-ttu-id="13fcd-126">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="13fcd-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="13fcd-127">**헤더:** 격리. h</span><span class="sxs-lookup"><span data-stu-id="13fcd-127">**Header:** Isolation.h</span></span>

<span data-ttu-id="13fcd-128">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13fcd-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="13fcd-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="13fcd-129">See also</span></span>

- [<span data-ttu-id="13fcd-130">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="13fcd-130">Fusion Interfaces</span></span>](fusion-interfaces.md)
