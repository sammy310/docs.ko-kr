---
title: GetMethod 함수 (관리 되지 않는 API 참조)
description: GetMethod 함수 메서드에 대 한 정보를 검색합니다.
ms.date: 11/06/2017
api_name:
- GetMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethod
helpviewer_keywords:
- GetMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 419fb33155cfa91199e52110da29efd44d606f4b
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636603"
---
# <a name="getmethod-function"></a><span data-ttu-id="9b736-103">GetMethod 함수</span><span class="sxs-lookup"><span data-stu-id="9b736-103">GetMethod function</span></span>

<span data-ttu-id="9b736-104">지정된 메서드에 대한 정보를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="9b736-104">Retrieves information about the specified method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="9b736-105">구문</span><span class="sxs-lookup"><span data-stu-id="9b736-105">Syntax</span></span>

```cpp
HRESULT GetMethod (
   [in] int                vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszName,
   [in] LONG                lFlags,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature
);
```

## <a name="parameters"></a><span data-ttu-id="9b736-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9b736-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="9b736-107">[in] 이 매개 변수 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b736-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="9b736-108">[in] 에 대 한 포인터를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="9b736-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="9b736-109">[in] 메서드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9b736-109">[in] The method name.</span></span> <span data-ttu-id="9b736-110">이 매개 변수 수 없습니다 `null` 유효한 가리켜야 `LPCWSTR`합니다.</span><span class="sxs-lookup"><span data-stu-id="9b736-110">This parameter cannot be `null` and must point to a valid `LPCWSTR`.</span></span>

`lFlags`\
<span data-ttu-id="9b736-111">[in] 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b736-111">[in] Reserved.</span></span> <span data-ttu-id="9b736-112">이 매개 변수는 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b736-112">This parameter must be 0.</span></span>

`ppInSignature`\
<span data-ttu-id="9b736-113">[out] 주소에 대 한 포인터를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 메서드에 in 매개 변수를 설명 하는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="9b736-113">[out] A pointer to the address of an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance that describes the in parameters to the method.</span></span> <span data-ttu-id="9b736-114">로 설정 된 경우이 매개 변수가 무시 됩니다 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="9b736-114">This parameter is ignored if it is set to `null`.</span></span>

`ppOutSignature`\
<span data-ttu-id="9b736-115">[out] 주소에 대 한 포인터를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 메서드에 out 매개 변수를 설명 하는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="9b736-115">[out] A pointer to the address of an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance that describes the out parameters to the method.</span></span> <span data-ttu-id="9b736-116">로 설정 된 경우이 매개 변수가 무시 됩니다 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="9b736-116">This parameter is ignored if it is set to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="9b736-117">반환 값</span><span class="sxs-lookup"><span data-stu-id="9b736-117">Return value</span></span>

<span data-ttu-id="9b736-118">이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="9b736-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="9b736-119">상수</span><span class="sxs-lookup"><span data-stu-id="9b736-119">Constant</span></span>  |<span data-ttu-id="9b736-120">값</span><span class="sxs-lookup"><span data-stu-id="9b736-120">Value</span></span>  |<span data-ttu-id="9b736-121">설명</span><span class="sxs-lookup"><span data-stu-id="9b736-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="9b736-122">0x80041002</span><span class="sxs-lookup"><span data-stu-id="9b736-122">0x80041002</span></span> | <span data-ttu-id="9b736-123">지정된 된 속성을 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9b736-123">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="9b736-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="9b736-124">0x80041006</span></span> | <span data-ttu-id="9b736-125">메모리가 부족 하 여 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9b736-125">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="9b736-126">0</span><span class="sxs-lookup"><span data-stu-id="9b736-126">0</span></span> | <span data-ttu-id="9b736-127">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9b736-127">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="9b736-128">설명</span><span class="sxs-lookup"><span data-stu-id="9b736-128">Remarks</span></span>

<span data-ttu-id="9b736-129">이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::GetMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) 메서드.</span><span class="sxs-lookup"><span data-stu-id="9b736-129">This function wraps a call to the [IWbemClassObject::GetMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) method.</span></span>

<span data-ttu-id="9b736-130">Windows 관리를 설정할 수는 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 에 대 한 포인터 `null` 메서드 매개 변수가 없는 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b736-130">Windows Management can set the [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointer to `null` if the method has no in parameters.</span></span>

<span data-ttu-id="9b736-131">`ppInSignature` 하 고 `ppOutSignature` in 및 out 매개 변수를 각각의 속성으로 설명를 `IWbemClassObject` 시스템 클래스의 인스턴스 [_Parameters](/windows/desktop/WmiSdk/--parameters)합니다.</span><span class="sxs-lookup"><span data-stu-id="9b736-131">In `ppInSignature` and `ppOutSignature` describe in and out parameters, respectively, as properties in a `IWbemClassObject` instance of the system class [_Parameters](/windows/desktop/WmiSdk/--parameters).</span></span> <span data-ttu-id="9b736-132">속성 `ppInSignature` 라고 `Param` *n*여기서 *n* 메서드 시그니처에서 매개 변수의 위치입니다 (같은 `Param1`, `Param2`등.).</span><span class="sxs-lookup"><span data-stu-id="9b736-132">The properties in `ppInSignature` are named `Param`*n*, where *n* is the position of the parameter in the method signature (such as `Param1`, `Param2`, etc.).</span></span> <span data-ttu-id="9b736-133">속성 `ppOutSignature` 이 라고도 `Param` *n*, 및 반환 값은 명명 된 `ReturnValue`합니다.</span><span class="sxs-lookup"><span data-stu-id="9b736-133">The properties in `ppOutSignature` are also named `Param`*n*, and the return value is named `ReturnValue`.</span></span> <span data-ttu-id="9b736-134">자세한 내용 및 예제를 참조 하세요 [IWbemClassObject::GetMethod 메서드](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod)합니다.</span><span class="sxs-lookup"><span data-stu-id="9b736-134">For more information and an example, see [IWbemClassObject::GetMethod method](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod).</span></span>

## <a name="requirements"></a><span data-ttu-id="9b736-135">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9b736-135">Requirements</span></span>

<span data-ttu-id="9b736-136">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9b736-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="9b736-137">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="9b736-137">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="9b736-138">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9b736-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="9b736-139">참고자료</span><span class="sxs-lookup"><span data-stu-id="9b736-139">See also</span></span>

- [<span data-ttu-id="9b736-140">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="9b736-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
