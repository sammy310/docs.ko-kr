---
title: 복제 함수(관리되지 않는 API 참조)
description: 복제 함수는 현재 개체의 전체 복제인 새 개체를 반환합니다.
ms.date: 11/06/2017
api_name:
- Clone
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Clone
helpviewer_keywords:
- Clone function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: cb4951a1f289417482bfa1287028cc66349a5938
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176853"
---
# <a name="clone-function"></a><span data-ttu-id="be1ad-103">Clone 함수</span><span class="sxs-lookup"><span data-stu-id="be1ad-103">Clone function</span></span>
<span data-ttu-id="be1ad-104">현재 개체의 전체 복제본인 새 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="be1ad-104">Returns a new object that is a complete clone of the current object.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="be1ad-105">구문</span><span class="sxs-lookup"><span data-stu-id="be1ad-105">Syntax</span></span>  
  
```cpp  
HRESULT Clone (
   [in] int                  vFunc,
   [in] IWbemClassObject*    ptr,
   [out] IWbemClassObject**  ppCopy
);
```  

## <a name="parameters"></a><span data-ttu-id="be1ad-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="be1ad-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="be1ad-107">【인】 이 매개 변수는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be1ad-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="be1ad-108">【인】 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="be1ad-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppCopy`  
<span data-ttu-id="be1ad-109">【아웃】 의 완전한 외로운 새 `ptr`개체입니다.</span><span class="sxs-lookup"><span data-stu-id="be1ad-109">[out] A new object that is a complete lone of `ptr`.</span></span> <span data-ttu-id="be1ad-110">이 인수는 `null` 현재 개체의 복사본을 받는 경우일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="be1ad-110">This argument cannot be `null` if it receives the copy of the current object.</span></span>

## <a name="return-value"></a><span data-ttu-id="be1ad-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="be1ad-111">Return value</span></span>

<span data-ttu-id="be1ad-112">이 함수에서 반환되는 다음 값은 *WbemCli.h* 헤더 파일에 정의되거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be1ad-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="be1ad-113">지속적임</span><span class="sxs-lookup"><span data-stu-id="be1ad-113">Constant</span></span>  |<span data-ttu-id="be1ad-114">값</span><span class="sxs-lookup"><span data-stu-id="be1ad-114">Value</span></span>  |<span data-ttu-id="be1ad-115">Description</span><span class="sxs-lookup"><span data-stu-id="be1ad-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="be1ad-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="be1ad-116">0x80041001</span></span> | <span data-ttu-id="be1ad-117">일반적인 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="be1ad-117">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="be1ad-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="be1ad-118">0x80041008</span></span> | <span data-ttu-id="be1ad-119">`null`매개 변수로 지정되었으며 이 사용에서는 합법적이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be1ad-119">`null` was specified as a parameter, and it is not legal in this usage.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="be1ad-120">0x80041006</span><span class="sxs-lookup"><span data-stu-id="be1ad-120">0x80041006</span></span> | <span data-ttu-id="be1ad-121">개체를 복제할 수 있는 메모리가 부족합니다.</span><span class="sxs-lookup"><span data-stu-id="be1ad-121">Not enough memory is available to clone the object.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="be1ad-122">0</span><span class="sxs-lookup"><span data-stu-id="be1ad-122">0</span></span> | <span data-ttu-id="be1ad-123">함수 호출이 성공했습니다.</span><span class="sxs-lookup"><span data-stu-id="be1ad-123">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="be1ad-124">설명</span><span class="sxs-lookup"><span data-stu-id="be1ad-124">Remarks</span></span>

<span data-ttu-id="be1ad-125">이 함수는 [IWbemClassObject::복제](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) 메서드에 대한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="be1ad-125">This function wraps a call to the [IWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) method.</span></span>

<span data-ttu-id="be1ad-126">복제된 개체는 참조 수가 1인 COM 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="be1ad-126">The cloned object is a COM object that has a reference count of 1.</span></span>

## <a name="requirements"></a><span data-ttu-id="be1ad-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="be1ad-127">Requirements</span></span>  
 <span data-ttu-id="be1ad-128">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="be1ad-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be1ad-129">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="be1ad-129">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="be1ad-130">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="be1ad-130">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be1ad-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="be1ad-131">See also</span></span>

- [<span data-ttu-id="be1ad-132">WMI 및 성능 카운터(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="be1ad-132">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
