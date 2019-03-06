---
title: Delete 함수 (관리 되지 않는 API 참조)
description: Delete 함수는 CIM 클래스 정의에서 지정된 된 속성 및 모든 해당 한정자를 삭제합니다.
ms.date: 11/06/2017
api_name:
- Delete
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Delete
helpviewer_keywords:
- Delete function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a1a26db7785a8a378fa541308ecc6aee30fa87ec
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57367129"
---
# <a name="delete-function"></a><span data-ttu-id="e473e-103">함수 삭제</span><span class="sxs-lookup"><span data-stu-id="e473e-103">Delete function</span></span>

<span data-ttu-id="e473e-104">CIM 클래스 정의에서 지정된 된 속성 및 모든 해당 한정자를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="e473e-104">Deletes the specified property and all of its qualifiers from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="e473e-105">구문</span><span class="sxs-lookup"><span data-stu-id="e473e-105">Syntax</span></span>

```cpp
HRESULT Delete (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName
);
```

## <a name="parameters"></a><span data-ttu-id="e473e-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e473e-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="e473e-107">[in] 이 매개 변수 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e473e-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="e473e-108">[in] 에 대 한 포인터를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="e473e-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="e473e-109">[in] 삭제할 속성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e473e-109">[in] The name of the property to delete.</span></span> <span data-ttu-id="e473e-110">`wszName` 유효한 포인터 여야 합니다. `LPCWSTR`합니다.</span><span class="sxs-lookup"><span data-stu-id="e473e-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="e473e-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="e473e-111">Return value</span></span>

<span data-ttu-id="e473e-112">이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="e473e-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e473e-113">상수</span><span class="sxs-lookup"><span data-stu-id="e473e-113">Constant</span></span>  |<span data-ttu-id="e473e-114">값</span><span class="sxs-lookup"><span data-stu-id="e473e-114">Value</span></span>  |<span data-ttu-id="e473e-115">설명</span><span class="sxs-lookup"><span data-stu-id="e473e-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="e473e-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="e473e-116">0x80041001</span></span> | <span data-ttu-id="e473e-117">지정 되지 않은 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e473e-117">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_OPERATION` | <span data-ttu-id="e473e-118">0x80041016</span><span class="sxs-lookup"><span data-stu-id="e473e-118">0x80041016</span></span> | <span data-ttu-id="e473e-119">속성을 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e473e-119">The property cannot be deleted.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="e473e-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="e473e-120">0x80041008</span></span> | <span data-ttu-id="e473e-121">`wszName`이 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e473e-121">`wszName` is invalid.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="e473e-122">0x80041002</span><span class="sxs-lookup"><span data-stu-id="e473e-122">0x80041002</span></span> | <span data-ttu-id="e473e-123">지정된 된 속성이 존재 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e473e-123">The specified property does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="e473e-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="e473e-124">0x80041006</span></span> | <span data-ttu-id="e473e-125">메모리가 부족 하 여 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e473e-125">There is not enough memory to complete the operation.</span></span> |
| `WBEM_E_PROPAGATED_PROPERTY` | <span data-ttu-id="e473e-126">0x8004101c</span><span class="sxs-lookup"><span data-stu-id="e473e-126">0x8004101c</span></span> | <span data-ttu-id="e473e-127">속성은 기본 클래스에서 상속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e473e-127">The property is inherited from a base class.</span></span> |
| `WBEM_E_SYSTEM_PROPERTY` | | <span data-ttu-id="e473e-128">속성은 시스템 속성이입니다.</span><span class="sxs-lookup"><span data-stu-id="e473e-128">The property is a system property.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="e473e-129">0</span><span class="sxs-lookup"><span data-stu-id="e473e-129">0</span></span> | <span data-ttu-id="e473e-130">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e473e-130">The function call was successful.</span></span>  |
| `WBEM_E_RESET_TO_DEFAULT` | <span data-ttu-id="e473e-131">0x80041030</span><span class="sxs-lookup"><span data-stu-id="e473e-131">0x80041030</span></span> | <span data-ttu-id="e473e-132">함수는 현재 클래스의 재정의 기본값을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="e473e-132">The function deleted an override default value for the current class.</span></span> <span data-ttu-id="e473e-133">부모 클래스에서이 속성의 기본값 다시 활성화 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e473e-133">The default value for this property in the parent class has been reactivated.</span></span> |

## <a name="remarks"></a><span data-ttu-id="e473e-134">설명</span><span class="sxs-lookup"><span data-stu-id="e473e-134">Remarks</span></span>

<span data-ttu-id="e473e-135">이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-delete) 메서드.</span><span class="sxs-lookup"><span data-stu-id="e473e-135">This function wraps a call to the [IWbemClassObject::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-delete) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="e473e-136">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e473e-136">Requirements</span></span>

<span data-ttu-id="e473e-137">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e473e-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="e473e-138">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="e473e-138">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="e473e-139">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e473e-139">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="e473e-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="e473e-140">See also</span></span>

- [<span data-ttu-id="e473e-141">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="e473e-141">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)