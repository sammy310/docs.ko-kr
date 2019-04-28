---
title: GetPropertyOrigin 함수 (관리 되지 않는 API 참조)
description: GetPropertyOrigin 함수 속성 선언 되는 클래스를 결정 합니다.
ms.date: 11/06/2017
api_name:
- GetPropertyOrigin
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyOrigin
helpviewer_keywords:
- GetPropertyOrigin function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 42e5cd6ee438b33fd07fd7c3242cc3c2a6513dd9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61723259"
---
# <a name="getpropertyorigin-function"></a><span data-ttu-id="656ef-103">GetPropertyOrigin 함수</span><span class="sxs-lookup"><span data-stu-id="656ef-103">GetPropertyOrigin function</span></span>

<span data-ttu-id="656ef-104">속성이 선언되는 클래스를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="656ef-104">Determines the class in which a property is declared.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="656ef-105">구문</span><span class="sxs-lookup"><span data-stu-id="656ef-105">Syntax</span></span>

```cpp
HRESULT GetPropertyOrigin (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
);
```

## <a name="parameters"></a><span data-ttu-id="656ef-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="656ef-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="656ef-107">[in] 이 매개 변수 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="656ef-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="656ef-108">[in] 에 대 한 포인터를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="656ef-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethodName`\
<span data-ttu-id="656ef-109">[in] 소유 하는 클래스를 요청 하는 개체에 대 한 속성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="656ef-109">[in] The name of the property for the object whose owning class is being requested.</span></span>

`pstrClassName`\
<span data-ttu-id="656ef-110">[out] 속성을 소유 하는 클래스의 이름을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="656ef-110">[out] Receives the name of the class that owns the property.</span></span>

## <a name="return-value"></a><span data-ttu-id="656ef-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="656ef-111">Return value</span></span>

<span data-ttu-id="656ef-112">이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="656ef-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="656ef-113">상수</span><span class="sxs-lookup"><span data-stu-id="656ef-113">Constant</span></span>  |<span data-ttu-id="656ef-114">값</span><span class="sxs-lookup"><span data-stu-id="656ef-114">Value</span></span>  |<span data-ttu-id="656ef-115">설명</span><span class="sxs-lookup"><span data-stu-id="656ef-115">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="656ef-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="656ef-116">0x80041001</span></span> | <span data-ttu-id="656ef-117">일반 오류가 발생이 했습니다.</span><span class="sxs-lookup"><span data-stu-id="656ef-117">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="656ef-118">0x80041002</span><span class="sxs-lookup"><span data-stu-id="656ef-118">0x80041002</span></span> | <span data-ttu-id="656ef-119">지정된 된 속성을 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="656ef-119">The specified property was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="656ef-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="656ef-120">0x80041008</span></span> | <span data-ttu-id="656ef-121">매개 변수가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="656ef-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="656ef-122">0x80041006</span><span class="sxs-lookup"><span data-stu-id="656ef-122">0x80041006</span></span> | <span data-ttu-id="656ef-123">메모리가 부족 하 여 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="656ef-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="656ef-124">0</span><span class="sxs-lookup"><span data-stu-id="656ef-124">0</span></span> | <span data-ttu-id="656ef-125">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="656ef-125">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="656ef-126">설명</span><span class="sxs-lookup"><span data-stu-id="656ef-126">Remarks</span></span>

<span data-ttu-id="656ef-127">이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::GetPropertyOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyorigin) 메서드.</span><span class="sxs-lookup"><span data-stu-id="656ef-127">This function wraps a call to the [IWbemClassObject::GetPropertyOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyorigin) method.</span></span>

<span data-ttu-id="656ef-128">클래스는 하나 이상의 기본 클래스에서 속성을 상속할 수 있습니다, 되므로 개발자는 종종 지정된 된 메서드에 정의 되어 있는 속성을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="656ef-128">Because a class can inherit properties from one or more base classes, developers often want to determine the property in which a given method is defined.</span></span>

<span data-ttu-id="656ef-129">`pstrClassName` 유효한 매개 변수를 가리키지 해야 `BSTR` 이기 때문에 함수를 호출 하기 전에 `out` 매개 변수;이 함수에서 반환 된 후 포인터 할당이 해제 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="656ef-129">The `pstrClassName` parameter must not point to a valid `BSTR` before the function is called because this is an `out` parameter; this pointer is not deallocated after the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="656ef-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="656ef-130">Requirements</span></span>

<span data-ttu-id="656ef-131">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="656ef-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="656ef-132">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="656ef-132">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="656ef-133">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="656ef-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="656ef-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="656ef-134">See also</span></span>

- [<span data-ttu-id="656ef-135">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="656ef-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)