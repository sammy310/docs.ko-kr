---
title: Clone 함수 (관리 되지 않는 API 참조)
description: Clone 함수는 현재 항목의 전체 복제본 인 새 개체를 반환 합니다.
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
ms.openlocfilehash: aecbf750b42626629dcb5aef369978a2e2bd002a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708116"
---
# <a name="clone-function"></a><span data-ttu-id="073b0-103">Clone 함수</span><span class="sxs-lookup"><span data-stu-id="073b0-103">Clone function</span></span>

<span data-ttu-id="073b0-104">현재 개체의 전체 복제본인 새 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="073b0-104">Returns a new object that is a complete clone of the current object.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="073b0-105">구문</span><span class="sxs-lookup"><span data-stu-id="073b0-105">Syntax</span></span>  
  
```cpp  
HRESULT Clone (
   [in] int                  vFunc,
   [in] IWbemClassObject*    ptr,
   [out] IWbemClassObject**  ppCopy
);
```  

## <a name="parameters"></a><span data-ttu-id="073b0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="073b0-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="073b0-107">진행 이 매개 변수는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="073b0-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="073b0-108">진행 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="073b0-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppCopy`  
<span data-ttu-id="073b0-109">제한이 의 전체 유일한 새 개체입니다 `ptr` .</span><span class="sxs-lookup"><span data-stu-id="073b0-109">[out] A new object that is a complete lone of `ptr`.</span></span> <span data-ttu-id="073b0-110">`null`현재 개체의 복사본을 받는 경우에는이 인수를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="073b0-110">This argument cannot be `null` if it receives the copy of the current object.</span></span>

## <a name="return-value"></a><span data-ttu-id="073b0-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="073b0-111">Return value</span></span>

<span data-ttu-id="073b0-112">이 함수에서 반환 되는 다음 값은 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="073b0-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="073b0-113">상수</span><span class="sxs-lookup"><span data-stu-id="073b0-113">Constant</span></span>  |<span data-ttu-id="073b0-114">값</span><span class="sxs-lookup"><span data-stu-id="073b0-114">Value</span></span>  |<span data-ttu-id="073b0-115">설명</span><span class="sxs-lookup"><span data-stu-id="073b0-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="073b0-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="073b0-116">0x80041001</span></span> | <span data-ttu-id="073b0-117">일반 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="073b0-117">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="073b0-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="073b0-118">0x80041008</span></span> | <span data-ttu-id="073b0-119">`null` 가 매개 변수로 지정 되었으며이 사용에 적합 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="073b0-119">`null` was specified as a parameter, and it is not legal in this usage.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="073b0-120">0x80041006</span><span class="sxs-lookup"><span data-stu-id="073b0-120">0x80041006</span></span> | <span data-ttu-id="073b0-121">개체를 복제 하는 데 사용할 수 있는 메모리가 부족 합니다.</span><span class="sxs-lookup"><span data-stu-id="073b0-121">Not enough memory is available to clone the object.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="073b0-122">0</span><span class="sxs-lookup"><span data-stu-id="073b0-122">0</span></span> | <span data-ttu-id="073b0-123">함수 호출에 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="073b0-123">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="073b0-124">설명</span><span class="sxs-lookup"><span data-stu-id="073b0-124">Remarks</span></span>

<span data-ttu-id="073b0-125">이 함수는 [IWbemClassObject:: Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) 메서드에 대 한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="073b0-125">This function wraps a call to the [IWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) method.</span></span>

<span data-ttu-id="073b0-126">복제 된 개체는 참조 개수가 1 인 COM 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="073b0-126">The cloned object is a COM object that has a reference count of 1.</span></span>

## <a name="requirements"></a><span data-ttu-id="073b0-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="073b0-127">Requirements</span></span>  

 <span data-ttu-id="073b0-128">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="073b0-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="073b0-129">**헤더:** WMINet_Utils idl</span><span class="sxs-lookup"><span data-stu-id="073b0-129">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="073b0-130">**.NET Framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="073b0-130">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="073b0-131">참조</span><span class="sxs-lookup"><span data-stu-id="073b0-131">See also</span></span>

- [<span data-ttu-id="073b0-132">WMI 및 성능 카운터(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="073b0-132">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
