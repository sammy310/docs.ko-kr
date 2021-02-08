---
description: '자세히 알아보기: IIdentityAuthority 인터페이스'
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
ms.openlocfilehash: 3064a3d95ebe9a098a7cac0766f18654c6fab8b9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800138"
---
# <a name="iidentityauthority-interface"></a><span data-ttu-id="3955f-103">IIdentityAuthority 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3955f-103">IIdentityAuthority Interface</span></span>

<span data-ttu-id="3955f-104">코드 개체에 대 한 id 키를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="3955f-104">Manages identity keys for code objects.</span></span>

## <a name="methods"></a><span data-ttu-id="3955f-105">메서드</span><span class="sxs-lookup"><span data-stu-id="3955f-105">Methods</span></span>

|<span data-ttu-id="3955f-106">메서드</span><span class="sxs-lookup"><span data-stu-id="3955f-106">Method</span></span>|<span data-ttu-id="3955f-107">설명</span><span class="sxs-lookup"><span data-stu-id="3955f-107">Description</span></span>|
|------------|-----------------|
|`IIdentityAuthority::AreDefinitionsEqual`|<span data-ttu-id="3955f-108">지정 된 두 [Idefinitionidentity](idefinitionidentity-interface.md) 인스턴스가 같은지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3955f-108">Gets a value that indicates whether the two specified [IDefinitionIdentity](idefinitionidentity-interface.md) instances are equal.</span></span>|
|`IIdentityAuthority::AreReferencesEqual`|<span data-ttu-id="3955f-109">지정 된 두 [IReferenceIdentity](ireferenceidentity-interface.md) 인스턴스가 같은지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3955f-109">Gets a value that indicates whether the two specified [IReferenceIdentity](ireferenceidentity-interface.md) instances are equal.</span></span>|
|`IIdentityAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="3955f-110">지정 된 두 문자열 정의 id 표현이 같은지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3955f-110">Gets a value that indicates whether the two specified string definition identity representations are equal.</span></span>|
|`IIdentityAuthority::AreTextualReferencesEqual`|<span data-ttu-id="3955f-111">지정 된 두 문자열 참조 id 표현이 같은지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3955f-111">Gets a value that indicates whether the two specified string reference identity representations are equal.</span></span>|
|`IIdentityAuthority::CreateDefinition`|<span data-ttu-id="3955f-112">`IDefinitionIdentity`현재 범위에 있는 코드 개체를 나타내는 새 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3955f-112">Gets a pointer to a new `IDefinitionIdentity` instance that represents the code object in the current scope.</span></span>|
|`IIdentityAuthority::CreateReference`|<span data-ttu-id="3955f-113">`IReferenceIdentity`현재 범위에 있는 코드 개체를 나타내는 새 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3955f-113">Gets a pointer to a new `IReferenceIdentity` instance that represents the code object in the current scope.</span></span>|
|`IIdentityAuthority::DefinitionToText`|<span data-ttu-id="3955f-114">지정 된의 형식이 지정 된 문자열 버전을 가져옵니다 `IDefinitionIdentity` .</span><span class="sxs-lookup"><span data-stu-id="3955f-114">Gets a formatted string version of the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::DefinitionToTextBuffer`|<span data-ttu-id="3955f-115">지정 된 와이드 문자 버퍼를 지정 된의 문자열 버전으로 채웁니다 `IDefinitionIdentity` .</span><span class="sxs-lookup"><span data-stu-id="3955f-115">Fills the specified wide character buffer with a string version of the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="3955f-116">지정 된 `IDefinitionIdentity` 및 `IReferenceIdentity` 인스턴스가 동일한 코드 개체를 참조 하는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3955f-116">Gets a value that indicates whether the specified `IDefinitionIdentity` and `IReferenceIdentity` instances refer to the same code object.</span></span>|
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="3955f-117">지정 된 문자열이 동일한 코드 개체를 참조 하는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3955f-117">Gets a value that indicates whether the specified strings refer to the same code object.</span></span>|
|`IIdentityAuthority::GenerateDefinitionKey`|<span data-ttu-id="3955f-118">지정 된에 대해 새로 만든 문자열 키에 대 한 포인터를 가져옵니다 `IDefinitionIdentity` .</span><span class="sxs-lookup"><span data-stu-id="3955f-118">Gets a pointer to a newly created string key for the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::GenerateReferenceKey`|<span data-ttu-id="3955f-119">지정 된에 대해 새로 만든 문자열 키에 대 한 포인터를 가져옵니다 `IReferenceIdentity` .</span><span class="sxs-lookup"><span data-stu-id="3955f-119">Gets a pointer to a newly created string key for the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::HashDefinition`|<span data-ttu-id="3955f-120">지정 된에 대 한 해시 값을 가져옵니다 `IDefinitionIdentity` .</span><span class="sxs-lookup"><span data-stu-id="3955f-120">Gets a hash value for the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::HashReference`|<span data-ttu-id="3955f-121">지정 된에 대 한 해시 값을 가져옵니다 `IReferenceIdentity` .</span><span class="sxs-lookup"><span data-stu-id="3955f-121">Gets a hash value for the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::ReferenceToText`|<span data-ttu-id="3955f-122">지정 된의 형식이 지정 된 문자열 버전을 가져옵니다 `IReferenceIdentity` .</span><span class="sxs-lookup"><span data-stu-id="3955f-122">Gets a formatted string version of the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::ReferenceToTextBuffer`|<span data-ttu-id="3955f-123">지정 된 와이드 문자 버퍼를 지정 된의 문자열 버전으로 채웁니다 `IReferenceIdentity` .</span><span class="sxs-lookup"><span data-stu-id="3955f-123">Fills the specified wide character buffer with a string version of the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::TextToDefinition`|<span data-ttu-id="3955f-124">`IDefinitionIdentity`지정 된 형식이 지정 된 문자열에서 생성 된 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3955f-124">Gets an interface pointer to an `IDefinitionIdentity` instance generated from the specified formatted string.</span></span>|
|`IIdentityAuthority::TextToReference`|<span data-ttu-id="3955f-125">`IReferenceIdentity`지정 된 형식이 지정 된 문자열에서 생성 된 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3955f-125">Gets an interface pointer to an `IReferenceIdentity` instance generated from the specified formatted string.</span></span>|

## <a name="requirements"></a><span data-ttu-id="3955f-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3955f-126">Requirements</span></span>

<span data-ttu-id="3955f-127">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3955f-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="3955f-128">**헤더:** 격리. h</span><span class="sxs-lookup"><span data-stu-id="3955f-128">**Header:** Isolation.h</span></span>

<span data-ttu-id="3955f-129">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3955f-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="3955f-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3955f-130">See also</span></span>

- [<span data-ttu-id="3955f-131">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3955f-131">Fusion Interfaces</span></span>](fusion-interfaces.md)
