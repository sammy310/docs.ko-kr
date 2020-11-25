---
title: Next 함수 (관리 되지 않는 API 참조)
description: 다음 함수는 열거형의 다음 속성을 검색 합니다.
ms.date: 11/06/2017
api_name:
- Next
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Next
helpviewer_keywords:
- Next function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: c2a7fae32e82caae40a95bfdad10fa78082988ef
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726789"
---
# <a name="next-function"></a><span data-ttu-id="d28b4-103">Next 함수</span><span class="sxs-lookup"><span data-stu-id="d28b4-103">Next function</span></span>

<span data-ttu-id="d28b4-104">[Beginenumeration](beginenumeration.md)호출로 시작 하는 열거형의 다음 속성을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="d28b4-104">Retrieves the next property in an enumeration that begins with a call to [BeginEnumeration](beginenumeration.md).</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="d28b4-105">구문</span><span class="sxs-lookup"><span data-stu-id="d28b4-105">Syntax</span></span>

```cpp
HRESULT Next (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              lFlags,
   [out] BSTR*            pstrName,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor
);
```

## <a name="parameters"></a><span data-ttu-id="d28b4-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d28b4-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="d28b4-107">진행 이 매개 변수는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d28b4-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="d28b4-108">진행 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d28b4-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`\
<span data-ttu-id="d28b4-109">[in] 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d28b4-109">[in] Reserved.</span></span> <span data-ttu-id="d28b4-110">이 매개 변수는 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d28b4-110">This parameter must be 0.</span></span>

`pstrName`\
<span data-ttu-id="d28b4-111">제한이 `BSTR` 속성 이름을 포함 하는 새입니다.</span><span class="sxs-lookup"><span data-stu-id="d28b4-111">[out] A new `BSTR` that contains the property name.</span></span> <span data-ttu-id="d28b4-112">이름이 필요 하지 않은 경우이 매개 변수를로 설정할 수 있습니다 `null` .</span><span class="sxs-lookup"><span data-stu-id="d28b4-112">You can set this parameter to `null` if the name is not required.</span></span>

`pVal`\
<span data-ttu-id="d28b4-113">제한이 `VARIANT` 속성의 값을 사용 하 여 채워진입니다.</span><span class="sxs-lookup"><span data-stu-id="d28b4-113">[out] A `VARIANT` filled with the value of the property.</span></span> <span data-ttu-id="d28b4-114">`null`값이 필요 하지 않은 경우이 매개 변수를로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d28b4-114">You can set this parameter to `null` if the value is not required.</span></span> <span data-ttu-id="d28b4-115">함수에서 오류 코드를 반환 하는 경우 `VARIANT` 에 전달 된는 `pVal` 수정 되지 않은 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d28b4-115">If the function returns an error code, the `VARIANT` passed to `pVal` is left unmodified.</span></span>

`pvtType`\
<span data-ttu-id="d28b4-116">제한이 `CIMTYPE` `LONG` 속성의 형식이 배치 되는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d28b4-116">[out] A pointer to a `CIMTYPE` variable (a `LONG` into which the type of the property is placed).</span></span> <span data-ttu-id="d28b4-117">이 속성의 값은 일 수 있으며 `VT_NULL_VARIANT` ,이 경우 속성의 실제 형식을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d28b4-117">The value of this property can be a `VT_NULL_VARIANT`, in which case it is necessary to determine the actual type of the property.</span></span> <span data-ttu-id="d28b4-118">이 매개 변수는 일 수도 있습니다 `null` .</span><span class="sxs-lookup"><span data-stu-id="d28b4-118">This parameter can also be `null`.</span></span>

`plFlavor`\
<span data-ttu-id="d28b4-119">[out] `null` 속성의 출처에 대 한 정보를 받는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d28b4-119">[out] `null`, or a value that receives information on the origin of the property.</span></span> <span data-ttu-id="d28b4-120">가능한 값은 [설명] 단원을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d28b4-120">See the [Remarks] section for possible values.</span></span>

## <a name="return-value"></a><span data-ttu-id="d28b4-121">반환 값</span><span class="sxs-lookup"><span data-stu-id="d28b4-121">Return value</span></span>

<span data-ttu-id="d28b4-122">이 함수에서 반환 되는 다음 값은 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d28b4-122">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="d28b4-123">상수</span><span class="sxs-lookup"><span data-stu-id="d28b4-123">Constant</span></span>  |<span data-ttu-id="d28b4-124">값</span><span class="sxs-lookup"><span data-stu-id="d28b4-124">Value</span></span>  |<span data-ttu-id="d28b4-125">설명</span><span class="sxs-lookup"><span data-stu-id="d28b4-125">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="d28b4-126">0x80041001</span><span class="sxs-lookup"><span data-stu-id="d28b4-126">0x80041001</span></span> | <span data-ttu-id="d28b4-127">일반 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d28b4-127">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="d28b4-128">0x80041008</span><span class="sxs-lookup"><span data-stu-id="d28b4-128">0x80041008</span></span> | <span data-ttu-id="d28b4-129">매개 변수가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d28b4-129">A parameter is invalid.</span></span> |
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="d28b4-130">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="d28b4-130">0x8004101d</span></span> | <span data-ttu-id="d28b4-131">함수를 호출 하지 않았습니다 [`BeginEnumeration`](beginenumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="d28b4-131">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="d28b4-132">0x80041006</span><span class="sxs-lookup"><span data-stu-id="d28b4-132">0x80041006</span></span> | <span data-ttu-id="d28b4-133">메모리가 부족 하 여 새 열거를 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d28b4-133">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="d28b4-134">0x80041015</span><span class="sxs-lookup"><span data-stu-id="d28b4-134">0x80041015</span></span> | <span data-ttu-id="d28b4-135">현재 프로세스와 Windows Management 간의 원격 프로시저 호출에 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d28b4-135">The remote procedure call between the current process and Windows Management failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="d28b4-136">0</span><span class="sxs-lookup"><span data-stu-id="d28b4-136">0</span></span> | <span data-ttu-id="d28b4-137">함수 호출에 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d28b4-137">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="d28b4-138">0x40005</span><span class="sxs-lookup"><span data-stu-id="d28b4-138">0x40005</span></span> | <span data-ttu-id="d28b4-139">열거형에 속성이 더 이상 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d28b4-139">There are no more properties in the enumeration.</span></span> |

## <a name="remarks"></a><span data-ttu-id="d28b4-140">설명</span><span class="sxs-lookup"><span data-stu-id="d28b4-140">Remarks</span></span>

<span data-ttu-id="d28b4-141">이 함수는 [IWbemClassObject:: Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-next) 메서드에 대 한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="d28b4-141">This function wraps a call to the [IWbemClassObject::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-next) method.</span></span>

<span data-ttu-id="d28b4-142">또한이 메서드는 시스템 속성을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d28b4-142">This method also returns system properties.</span></span>

<span data-ttu-id="d28b4-143">속성의 기본 형식이 개체 경로, 날짜 또는 시간 또는 다른 특수 형식인 경우 반환 된 형식에는 충분 한 정보가 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d28b4-143">If the underlying type of the property is an object path, a date or time, or another special type, then the returned type does not contain enough information.</span></span> <span data-ttu-id="d28b4-144">호출자는 `CIMTYPE` 지정 된 속성에 대 한를 검사 하 여 속성이 개체 참조, 날짜 또는 시간 또는 다른 특수 형식 인지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d28b4-144">The caller must examine the `CIMTYPE` for the specified property to determine if the property is an object reference, a date or time, or another special type.</span></span>

<span data-ttu-id="d28b4-145">`plFlavor`가이 아니면 `null` 값은 다음과 `LONG` 같이 속성의 원본에 대 한 정보를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="d28b4-145">If `plFlavor` is not `null`, the `LONG` value receives information about the origin of the property, as follows:</span></span>

|<span data-ttu-id="d28b4-146">상수</span><span class="sxs-lookup"><span data-stu-id="d28b4-146">Constant</span></span>  |<span data-ttu-id="d28b4-147">값</span><span class="sxs-lookup"><span data-stu-id="d28b4-147">Value</span></span>  |<span data-ttu-id="d28b4-148">설명</span><span class="sxs-lookup"><span data-stu-id="d28b4-148">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | <span data-ttu-id="d28b4-149">0x40</span><span class="sxs-lookup"><span data-stu-id="d28b4-149">0x40</span></span> | <span data-ttu-id="d28b4-150">속성은 표준 시스템 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d28b4-150">The property is a standard system property.</span></span> |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | <span data-ttu-id="d28b4-151">0x20</span><span class="sxs-lookup"><span data-stu-id="d28b4-151">0x20</span></span> | <span data-ttu-id="d28b4-152">클래스의 경우: 속성은 부모 클래스에서 상속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d28b4-152">For a class: The property is inherited from the parent class.</span></span> <br> <span data-ttu-id="d28b4-153">인스턴스의 경우: 부모 클래스에서 상속 된 속성은 인스턴스에 의해 수정 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="d28b4-153">For an instance: The property, while inherited from the parent class, has not been modified by the instance.</span></span>  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | <span data-ttu-id="d28b4-154">0</span><span class="sxs-lookup"><span data-stu-id="d28b4-154">0</span></span> | <span data-ttu-id="d28b4-155">클래스의 경우: 속성이 파생 클래스에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="d28b4-155">For a class: The property belongs to the derived class.</span></span> <br> <span data-ttu-id="d28b4-156">인스턴스의 경우: 속성은 인스턴스에 의해 수정 됩니다. 즉, 값을 제공 했거나 한정자를 추가 하거나 수정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d28b4-156">For an instance: The property is modified by the instance; that is, a value was supplied, or a qualifier was added or modified.</span></span> |

## <a name="requirements"></a><span data-ttu-id="d28b4-157">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d28b4-157">Requirements</span></span>

<span data-ttu-id="d28b4-158">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d28b4-158">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="d28b4-159">**헤더:** WMINet_Utils idl</span><span class="sxs-lookup"><span data-stu-id="d28b4-159">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="d28b4-160">**.NET Framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d28b4-160">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="d28b4-161">참조</span><span class="sxs-lookup"><span data-stu-id="d28b4-161">See also</span></span>

- [<span data-ttu-id="d28b4-162">WMI 및 성능 카운터(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="d28b4-162">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
