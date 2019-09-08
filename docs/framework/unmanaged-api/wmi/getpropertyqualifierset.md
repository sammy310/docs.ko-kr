---
title: GetPropertyQualifierSet 함수 (관리 되지 않는 API 참조)
description: GetPropertyQualifierSet 함수는 속성에 대 한 한정자 집합을 검색 합니다.
ms.date: 11/06/2017
api_name:
- GetPropertyQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyQualifierSet
helpviewer_keywords:
- GetPropertyQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7bce241d10051e4c6be94cdfa40de23773fb0bb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798478"
---
# <a name="getpropertyqualifierset-function"></a><span data-ttu-id="72eaf-103">GetPropertyQualifierSet 함수</span><span class="sxs-lookup"><span data-stu-id="72eaf-103">GetPropertyQualifierSet function</span></span>

<span data-ttu-id="72eaf-104">특정 속성에 대한 한정자 집합을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="72eaf-104">Retrieves the qualifier set for a particular property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="72eaf-105">구문</span><span class="sxs-lookup"><span data-stu-id="72eaf-105">Syntax</span></span>

```cpp
HRESULT GetPropertyQualifierSet (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszProperty,
   [out] IWbemQualifierSet  **ppQualSet
);
```

## <a name="parameters"></a><span data-ttu-id="72eaf-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="72eaf-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="72eaf-107">진행 이 매개 변수는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="72eaf-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="72eaf-108">진행 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="72eaf-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethod`\
<span data-ttu-id="72eaf-109">진행 속성 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="72eaf-109">[in] The property  name.</span></span> <span data-ttu-id="72eaf-110">`wszProperty`는 유효한 `LPCWSTR`을 가리켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72eaf-110">`wszProperty` must point to a valid `LPCWSTR`.</span></span>

`ppQualSet`\
<span data-ttu-id="72eaf-111">제한이 속성 한정자에 대 한 액세스를 허용 하는 인터페이스 포인터를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="72eaf-111">[out] Receives the interface pointer that allows access to the qualifiers of the property.</span></span> <span data-ttu-id="72eaf-112">`ppQualSet`가 `null`이 될 수 없는 경우</span><span class="sxs-lookup"><span data-stu-id="72eaf-112">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="72eaf-113">오류가 발생 하면 새 개체가 반환 되지 않고 포인터가를 `null`가리키도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="72eaf-113">If an error occurs, a new object is not returned, and the pointer is set to point to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="72eaf-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="72eaf-114">Return value</span></span>

<span data-ttu-id="72eaf-115">이 함수에서 반환 되는 다음 값은 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72eaf-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="72eaf-116">상수</span><span class="sxs-lookup"><span data-stu-id="72eaf-116">Constant</span></span>  |<span data-ttu-id="72eaf-117">값</span><span class="sxs-lookup"><span data-stu-id="72eaf-117">Value</span></span>  |<span data-ttu-id="72eaf-118">Description</span><span class="sxs-lookup"><span data-stu-id="72eaf-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="72eaf-119">0x80041001</span><span class="sxs-lookup"><span data-stu-id="72eaf-119">0x80041001</span></span> | <span data-ttu-id="72eaf-120">일반 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="72eaf-120">There has been a general failure.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="72eaf-121">0x80041002</span><span class="sxs-lookup"><span data-stu-id="72eaf-121">0x80041002</span></span> | <span data-ttu-id="72eaf-122">지정 된 메서드가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="72eaf-122">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="72eaf-123">0x80041006</span><span class="sxs-lookup"><span data-stu-id="72eaf-123">0x80041006</span></span> | <span data-ttu-id="72eaf-124">메모리가 부족 하 여 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="72eaf-124">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="72eaf-125">0x80041008</span><span class="sxs-lookup"><span data-stu-id="72eaf-125">0x80041008</span></span> | <span data-ttu-id="72eaf-126">매개 변수가 인 `null`경우</span><span class="sxs-lookup"><span data-stu-id="72eaf-126">A parameter is `null`.</span></span> |
| `WBEM_E_SYSTEM_PROPERTY` | <span data-ttu-id="72eaf-127">0x80041030</span><span class="sxs-lookup"><span data-stu-id="72eaf-127">0x80041030</span></span> | <span data-ttu-id="72eaf-128">함수는 시스템 속성의 한정자를 가져오려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="72eaf-128">The function attempts to get qualifiers of a system property.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="72eaf-129">0</span><span class="sxs-lookup"><span data-stu-id="72eaf-129">0</span></span> | <span data-ttu-id="72eaf-130">함수 호출에 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="72eaf-130">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="72eaf-131">설명</span><span class="sxs-lookup"><span data-stu-id="72eaf-131">Remarks</span></span>

<span data-ttu-id="72eaf-132">이 함수는 [IWbemClassObject:: GetPropertyQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyqualifierset) 메서드에 대 한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="72eaf-132">This function wraps a call to the [IWbemClassObject::GetPropertyQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyqualifierset) method.</span></span>

<span data-ttu-id="72eaf-133">이 함수에 대 한 호출은 현재 개체가 CIM 클래스 정의 인 경우에만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="72eaf-133">A call to this function is supported only if the current object is a CIM class definition.</span></span> <span data-ttu-id="72eaf-134">CIM 인스턴스를 가리키는 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 포인터에는 메서드 조작을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="72eaf-134">Method manipulation is not available for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

<span data-ttu-id="72eaf-135">각 메서드에는 자체 한정자가 있을 수 있으므로 [IWbemQualifierSet 포인터](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) 를 사용 하면 호출자가 이러한 한정자를 추가, 편집 또는 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72eaf-135">Because each method may have its own qualifiers, the [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span>

<span data-ttu-id="72eaf-136">시스템 속성에는 한정자가 없으므로 시스템 속성에 `WBEM_E_SYSTEM_PROPERTY` 대 한 [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) 포인터를 가져오려고 하면이 함수는를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="72eaf-136">Because system properties have no qualifiers, the function returns `WBEM_E_SYSTEM_PROPERTY` if you attempt to obtain a [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) pointer for a system property.</span></span>

## <a name="requirements"></a><span data-ttu-id="72eaf-137">요구 사항</span><span class="sxs-lookup"><span data-stu-id="72eaf-137">Requirements</span></span>

<span data-ttu-id="72eaf-138">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="72eaf-138">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="72eaf-139">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="72eaf-139">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="72eaf-140">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="72eaf-140">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="72eaf-141">참고자료</span><span class="sxs-lookup"><span data-stu-id="72eaf-141">See also</span></span>

- [<span data-ttu-id="72eaf-142">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="72eaf-142">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
