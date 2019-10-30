---
title: GetMethod 함수 (관리 되지 않는 API 참조)
description: GetMethod 함수는 메서드에 대 한 정보를 검색 합니다.
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
ms.openlocfilehash: 48986f5ff1cbbb45840ec1a059aa86711848d717
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73102583"
---
# <a name="getmethod-function"></a><span data-ttu-id="956a1-103">GetMethod 함수</span><span class="sxs-lookup"><span data-stu-id="956a1-103">GetMethod function</span></span>

<span data-ttu-id="956a1-104">지정된 메서드에 대한 정보를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="956a1-104">Retrieves information about the specified method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="956a1-105">구문</span><span class="sxs-lookup"><span data-stu-id="956a1-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="956a1-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="956a1-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="956a1-107">진행 이 매개 변수는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="956a1-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="956a1-108">진행 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="956a1-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="956a1-109">진행 메서드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="956a1-109">[in] The method name.</span></span> <span data-ttu-id="956a1-110">이 매개 변수는 `null` 수 없으며 유효한 `LPCWSTR`을 가리켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="956a1-110">This parameter cannot be `null` and must point to a valid `LPCWSTR`.</span></span>

`lFlags`\
<span data-ttu-id="956a1-111">[in] 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="956a1-111">[in] Reserved.</span></span> <span data-ttu-id="956a1-112">이 매개 변수는 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="956a1-112">This parameter must be 0.</span></span>

`ppInSignature`\
<span data-ttu-id="956a1-113">제한이 메서드에 대 한 in 매개 변수를 설명 하는 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="956a1-113">[out] A pointer to the address of an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance that describes the in parameters to the method.</span></span> <span data-ttu-id="956a1-114">이 매개 변수는 `null`로 설정 된 경우 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="956a1-114">This parameter is ignored if it is set to `null`.</span></span>

`ppOutSignature`\
<span data-ttu-id="956a1-115">제한이 메서드에 대 한 출력 매개 변수를 설명 하는 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="956a1-115">[out] A pointer to the address of an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance that describes the out parameters to the method.</span></span> <span data-ttu-id="956a1-116">이 매개 변수는 `null`로 설정 된 경우 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="956a1-116">This parameter is ignored if it is set to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="956a1-117">반환 값</span><span class="sxs-lookup"><span data-stu-id="956a1-117">Return value</span></span>

<span data-ttu-id="956a1-118">이 함수에서 반환 되는 다음 값은 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="956a1-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="956a1-119">상수</span><span class="sxs-lookup"><span data-stu-id="956a1-119">Constant</span></span>  |<span data-ttu-id="956a1-120">값</span><span class="sxs-lookup"><span data-stu-id="956a1-120">Value</span></span>  |<span data-ttu-id="956a1-121">설명</span><span class="sxs-lookup"><span data-stu-id="956a1-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="956a1-122">0x80041002</span><span class="sxs-lookup"><span data-stu-id="956a1-122">0x80041002</span></span> | <span data-ttu-id="956a1-123">지정 된 속성을 찾을 수 없는 경우</span><span class="sxs-lookup"><span data-stu-id="956a1-123">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="956a1-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="956a1-124">0x80041006</span></span> | <span data-ttu-id="956a1-125">메모리가 부족 하 여 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="956a1-125">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="956a1-126">0</span><span class="sxs-lookup"><span data-stu-id="956a1-126">0</span></span> | <span data-ttu-id="956a1-127">함수 호출에 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="956a1-127">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="956a1-128">주의</span><span class="sxs-lookup"><span data-stu-id="956a1-128">Remarks</span></span>

<span data-ttu-id="956a1-129">이 함수는 [IWbemClassObject:: GetMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) 메서드에 대 한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="956a1-129">This function wraps a call to the [IWbemClassObject::GetMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) method.</span></span>

<span data-ttu-id="956a1-130">Windows Management는 메서드에 in 매개 변수가 없는 경우 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 포인터를 `null`로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="956a1-130">Windows Management can set the [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointer to `null` if the method has no in parameters.</span></span>

<span data-ttu-id="956a1-131">`ppInSignature` 및 `ppOutSignature`에는 각 매개 변수에 대 한 설명 및 out 매개 변수를 시스템 클래스 [매개 변수](/windows/desktop/WmiSdk/--parameters)`IWbemClassObject` 인스턴스의 속성으로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="956a1-131">In `ppInSignature` and `ppOutSignature` describe in and out parameters, respectively, as properties in a `IWbemClassObject` instance of the system class [_Parameters](/windows/desktop/WmiSdk/--parameters).</span></span> <span data-ttu-id="956a1-132">`ppInSignature`의 속성 이름은 `Param`*n*으로 지정 됩니다. 여기서 *n* 은 메서드 시그니처의 매개 변수 위치 (예: `Param1`, `Param2`등)입니다.</span><span class="sxs-lookup"><span data-stu-id="956a1-132">The properties in `ppInSignature` are named `Param`*n*, where *n* is the position of the parameter in the method signature (such as `Param1`, `Param2`, etc.).</span></span> <span data-ttu-id="956a1-133">`ppOutSignature`의 속성도 이름이 `Param`*n*이 고 반환 값은 `ReturnValue`입니다.</span><span class="sxs-lookup"><span data-stu-id="956a1-133">The properties in `ppOutSignature` are also named `Param`*n*, and the return value is named `ReturnValue`.</span></span> <span data-ttu-id="956a1-134">자세한 내용 및 예제는 [IWbemClassObject:: GetMethod 메서드](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="956a1-134">For more information and an example, see [IWbemClassObject::GetMethod method](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod).</span></span>

## <a name="requirements"></a><span data-ttu-id="956a1-135">요구 사항</span><span class="sxs-lookup"><span data-stu-id="956a1-135">Requirements</span></span>

<span data-ttu-id="956a1-136">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="956a1-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="956a1-137">**헤더:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="956a1-137">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="956a1-138">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="956a1-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="956a1-139">참조</span><span class="sxs-lookup"><span data-stu-id="956a1-139">See also</span></span>

- [<span data-ttu-id="956a1-140">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="956a1-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
