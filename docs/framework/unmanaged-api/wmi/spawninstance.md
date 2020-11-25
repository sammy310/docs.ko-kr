---
title: SpawnInstance 함수 (관리 되지 않는 API 참조)
description: SpawnInstance 함수는 클래스의 새 인스턴스를 만듭니다.
ms.date: 11/06/2017
api_name:
- SpawnInstance
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SpawnInstance
helpviewer_keywords:
- SpawnInstance function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 176bc83dd02381af8c2bc3995a37e7fee7c1bebf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732231"
---
# <a name="spawninstance-function"></a><span data-ttu-id="3db99-103">SpawnInstance 함수</span><span class="sxs-lookup"><span data-stu-id="3db99-103">SpawnInstance function</span></span>

<span data-ttu-id="3db99-104">클래스의 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3db99-104">Creates a new instance of a class.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="3db99-105">구문</span><span class="sxs-lookup"><span data-stu-id="3db99-105">Syntax</span></span>  
  
```cpp  
HRESULT SpawnInstance (
   [in] int                  vFunc,
   [in] IWbemClassObject*    ptr,
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewInstance);
```  

## <a name="parameters"></a><span data-ttu-id="3db99-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3db99-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="3db99-107">진행 이 매개 변수는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3db99-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="3db99-108">진행 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3db99-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="3db99-109">[in] 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3db99-109">[in] Reserved.</span></span> <span data-ttu-id="3db99-110">이 매개 변수는 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3db99-110">This parameter must be 0.</span></span>

`ppNewInstance`  
<span data-ttu-id="3db99-111">제한이 클래스의 새 인스턴스에 대 한 포인터를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="3db99-111">[out] Receives the pointer to the new instance of the class.</span></span> <span data-ttu-id="3db99-112">오류가 발생 하면 새 개체가 반환 되지 않고 수정 되지 않은 `ppNewInstance` 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3db99-112">If an error occurs, a new object is not returned, and `ppNewInstance` is left unmodified.</span></span>

## <a name="return-value"></a><span data-ttu-id="3db99-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="3db99-113">Return value</span></span>

<span data-ttu-id="3db99-114">이 함수에서 반환 되는 다음 값은 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3db99-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="3db99-115">상수</span><span class="sxs-lookup"><span data-stu-id="3db99-115">Constant</span></span>  |<span data-ttu-id="3db99-116">값</span><span class="sxs-lookup"><span data-stu-id="3db99-116">Value</span></span>  |<span data-ttu-id="3db99-117">설명</span><span class="sxs-lookup"><span data-stu-id="3db99-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="3db99-118">0x80041020</span><span class="sxs-lookup"><span data-stu-id="3db99-118">0x80041020</span></span> | <span data-ttu-id="3db99-119">`ptr` 는 유효한 클래스 정의가 아니므로 새 인스턴스를 생성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3db99-119">`ptr` is not a valid class definition and cannot spawn new instances.</span></span> <span data-ttu-id="3db99-120">불완전 하거나 [PutClassWmi](putclasswmi.md)를 호출 하 여 Windows Management에 등록 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="3db99-120">Either it is incomplete or it has not been registered with Windows Management by calling [PutClassWmi](putclasswmi.md).</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="3db99-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="3db99-121">0x80041006</span></span> | <span data-ttu-id="3db99-122">메모리가 부족 하 여 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3db99-122">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="3db99-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="3db99-123">0x80041008</span></span> | <span data-ttu-id="3db99-124">`ppNewClass`이(가) `null`인 경우.</span><span class="sxs-lookup"><span data-stu-id="3db99-124">`ppNewClass` is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="3db99-125">0</span><span class="sxs-lookup"><span data-stu-id="3db99-125">0</span></span> | <span data-ttu-id="3db99-126">함수 호출에 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3db99-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="3db99-127">설명</span><span class="sxs-lookup"><span data-stu-id="3db99-127">Remarks</span></span>

<span data-ttu-id="3db99-128">이 함수는 [IWbemClassObject:: SpawnInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance) 메서드에 대 한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="3db99-128">This function wraps a call to the [IWbemClassObject::SpawnInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance) method.</span></span>

<span data-ttu-id="3db99-129">`ptr` 는 Windows Management에서 가져온 클래스 정의 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3db99-129">`ptr` must be a class definition obtained from Windows Management.</span></span> <span data-ttu-id="3db99-130">인스턴스에서 인스턴스를 생성 하는 것은 지원 되지만 반환 된 인스턴스는 비어 있습니다. 그런 다음이 클래스 정의를 사용 하 여 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3db99-130">(Note that spawning an instance from an instance is supported but the returned instance is empty.) You then use this class definition to create new instances.</span></span> <span data-ttu-id="3db99-131">Windows 관리에 인스턴스를 쓰려면 [Putinstancewmi](putinstancewmi.md) 함수를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3db99-131">A call to the [PutInstanceWmi](putinstancewmi.md) function is required if you intend to write the instance to Windows Management.</span></span>

<span data-ttu-id="3db99-132">에서 반환 되는 새 개체는 `ppNewClass` 자동으로 현재 개체의 서브 클래스가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3db99-132">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="3db99-133">이 동작은 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3db99-133">This behavior cannot be overridden.</span></span> <span data-ttu-id="3db99-134">서브 클래스 (파생 클래스)를 만들 수 있는 다른 방법은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3db99-134">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="3db99-135">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3db99-135">Requirements</span></span>  

 <span data-ttu-id="3db99-136">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3db99-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3db99-137">**헤더:** WMINet_Utils idl</span><span class="sxs-lookup"><span data-stu-id="3db99-137">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="3db99-138">**.NET Framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3db99-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3db99-139">참조</span><span class="sxs-lookup"><span data-stu-id="3db99-139">See also</span></span>

- [<span data-ttu-id="3db99-140">WMI 및 성능 카운터(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="3db99-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
