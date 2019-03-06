---
title: GetMethodQualifierSet 함수 (관리 되지 않는 API 참조)
description: GetMethodQualifierSet 함수 메서드의 한정자 집합을 검색합니다.
ms.date: 11/06/2017
api_name:
- GetMethodQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethodQualifierSet
helpviewer_keywords:
- GetMethodQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9257ba57e0d087e3d6b9c7bb995b49a6b814c5f1
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373610"
---
# <a name="getmethodqualifierset-function"></a><span data-ttu-id="81152-103">GetMethodQualifierSet 함수</span><span class="sxs-lookup"><span data-stu-id="81152-103">GetMethodQualifierSet function</span></span>

<span data-ttu-id="81152-104">특정 메서드에 대한 한정자 집합을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="81152-104">Retrieves the qualifier set for a particular method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="81152-105">구문</span><span class="sxs-lookup"><span data-stu-id="81152-105">Syntax</span></span>

```cpp
HRESULT GetMethodQualifierSet (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszMethod,
   [out] IWbemQualifierSet  **ppQualSet
);
```

## <a name="parameters"></a><span data-ttu-id="81152-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="81152-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="81152-107">[in] 이 매개 변수 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81152-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="81152-108">[in] 에 대 한 포인터를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="81152-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethod`\
<span data-ttu-id="81152-109">[in] 메서드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="81152-109">[in] The method  name.</span></span> <span data-ttu-id="81152-110">`wszMethod` 유효한 가리켜야 `LPCWSTR`합니다.</span><span class="sxs-lookup"><span data-stu-id="81152-110">`wszMethod` must point to a valid `LPCWSTR`.</span></span>

`ppQualSet`\
<span data-ttu-id="81152-111">[out] 메서드의 한정자에 대 한 액세스를 허용 하는 인터페이스 포인터를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="81152-111">[out] Receives the interface pointer that allows access to the qualifiers of the method.</span></span> <span data-ttu-id="81152-112">`ppQualSet`가 `null`이 될 수 없는 경우</span><span class="sxs-lookup"><span data-stu-id="81152-112">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="81152-113">오류가 발생 하는 경우 새 개체를 반환 되지 않으면 및 포인터를 가리키도록 설정 되어 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="81152-113">If an error occurs, a new object is not returned, and the pointer is set to point to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="81152-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="81152-114">Return value</span></span>

<span data-ttu-id="81152-115">이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="81152-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="81152-116">상수</span><span class="sxs-lookup"><span data-stu-id="81152-116">Constant</span></span>  |<span data-ttu-id="81152-117">값</span><span class="sxs-lookup"><span data-stu-id="81152-117">Value</span></span>  |<span data-ttu-id="81152-118">설명</span><span class="sxs-lookup"><span data-stu-id="81152-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="81152-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="81152-119">0x80041002</span></span> | <span data-ttu-id="81152-120">지정된 된 메서드가 존재 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81152-120">The specified method does not exist.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="81152-121">0x80041008</span><span class="sxs-lookup"><span data-stu-id="81152-121">0x80041008</span></span> | <span data-ttu-id="81152-122">매개 변수는 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="81152-122">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="81152-123">0</span><span class="sxs-lookup"><span data-stu-id="81152-123">0</span></span> | <span data-ttu-id="81152-124">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="81152-124">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="81152-125">설명</span><span class="sxs-lookup"><span data-stu-id="81152-125">Remarks</span></span>

<span data-ttu-id="81152-126">이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::GetMethodQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethodqualifierset) 메서드.</span><span class="sxs-lookup"><span data-stu-id="81152-126">This function wraps a call to the [IWbemClassObject::GetMethodQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethodqualifierset) method.</span></span>

<span data-ttu-id="81152-127">이 함수에 대 한 호출에는 현재 개체가 CIM 클래스 정의 하는 경우에 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81152-127">A call to this function is supported only if the current object is a CIM class definition.</span></span> <span data-ttu-id="81152-128">사용할 수 없는 메서드 조작 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) CIM 인스턴스를 가리키는 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="81152-128">Method manipulation is not available for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

<span data-ttu-id="81152-129">각 메서드는 자체 한정자가 있을 수 있으므로 합니다 [IWbemQualifierSet 포인터](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) 호출자가 추가, 편집 또는 이러한 한정자를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81152-129">Because each method may have its own qualifiers, the [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span>

## <a name="requirements"></a><span data-ttu-id="81152-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="81152-130">Requirements</span></span>

<span data-ttu-id="81152-131">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="81152-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="81152-132">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="81152-132">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="81152-133">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="81152-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="81152-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="81152-134">See also</span></span>

- [<span data-ttu-id="81152-135">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="81152-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)