---
title: SpawnDerivedClass 함수 (관리 되지 않는 API 참조)
description: SpawnDerivedClass 함수는 개체에서 파생 되는 새 개체를 만듭니다.
ms.date: 11/06/2017
api_name:
- SpawnDerivedClass
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SpawnDerivedClass
helpviewer_keywords:
- SpawnDerivedClass function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: f72e6b1c356077a94b141e40d6efe485e77e7a9e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120188"
---
# <a name="spawnderivedclass-function"></a><span data-ttu-id="56160-103">SpawnDerivedClass 함수</span><span class="sxs-lookup"><span data-stu-id="56160-103">SpawnDerivedClass function</span></span>
<span data-ttu-id="56160-104">지정된 개체에서 새로 파생된 클래스 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="56160-104">Creates a newly derived class object from a specified object.</span></span>    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="56160-105">구문</span><span class="sxs-lookup"><span data-stu-id="56160-105">Syntax</span></span>  
  
```cpp  
HRESULT SpawnDerivedClass (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewClass); 
```  

## <a name="parameters"></a><span data-ttu-id="56160-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="56160-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="56160-107">진행 이 매개 변수는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="56160-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="56160-108">진행 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="56160-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="56160-109">[in] 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56160-109">[in] Reserved.</span></span> <span data-ttu-id="56160-110">이 매개 변수는 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56160-110">This parameter must be 0.</span></span>

`ppNewClass`  
<span data-ttu-id="56160-111">제한이 새 클래스 정의 개체에 대 한 포인터를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="56160-111">[out] Receives the pointer to the new class definition object.</span></span> <span data-ttu-id="56160-112">오류가 발생 하면 새 개체가 반환 되지 않고 `ppNewClass`는 수정 되지 않은 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="56160-112">If an error occurs, a new object is not returned, and `ppNewClass` is left unmodified.</span></span> <span data-ttu-id="56160-113">해당 값은 `null`수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="56160-113">Its value cannot be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="56160-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="56160-114">Return value</span></span>

<span data-ttu-id="56160-115">이 함수에서 반환 되는 다음 값은 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56160-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="56160-116">상수</span><span class="sxs-lookup"><span data-stu-id="56160-116">Constant</span></span>  |<span data-ttu-id="56160-117">값</span><span class="sxs-lookup"><span data-stu-id="56160-117">Value</span></span>  |<span data-ttu-id="56160-118">설명</span><span class="sxs-lookup"><span data-stu-id="56160-118">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="56160-119">0x80041001</span><span class="sxs-lookup"><span data-stu-id="56160-119">0x80041001</span></span> | <span data-ttu-id="56160-120">일반 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="56160-120">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_OPERATION` | <span data-ttu-id="56160-121">0x80041016</span><span class="sxs-lookup"><span data-stu-id="56160-121">0x80041016</span></span> | <span data-ttu-id="56160-122">인스턴스에서 클래스를 생성 하는 등의 잘못 된 작업이 요청 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="56160-122">An invalid operation, such as spawning a class from an instance, was requested.</span></span> |
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="56160-123">소스 클래스가 완전히 정의 되지 않았거나 Windows Management에 등록 되어 있지 않으므로 새 파생 클래스가 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="56160-123">The source class was not completely defined or registered with Windows Management, so a new derived class is not permitted.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="56160-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="56160-124">0x80041006</span></span> | <span data-ttu-id="56160-125">메모리가 부족 하 여 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="56160-125">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="56160-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="56160-126">0x80041008</span></span> | <span data-ttu-id="56160-127">`ppNewClass`가 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="56160-127">`ppNewClass` is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="56160-128">0</span><span class="sxs-lookup"><span data-stu-id="56160-128">0</span></span> | <span data-ttu-id="56160-129">함수 호출에 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="56160-129">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="56160-130">주의</span><span class="sxs-lookup"><span data-stu-id="56160-130">Remarks</span></span>

<span data-ttu-id="56160-131">이 함수는 [IWbemClassObject:: SpawnDerivedClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) 메서드에 대 한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="56160-131">This function wraps a call to the [IWbemClassObject::SpawnDerivedClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) method.</span></span>

<span data-ttu-id="56160-132">`ptr`는 생성 된 개체의 부모 클래스가 되는 클래스 정의 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56160-132">`ptr` must be a class definition that becomes the parent class of the spawned object.</span></span> <span data-ttu-id="56160-133">반환 된 개체는 현재 개체의 서브 클래스가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="56160-133">The returned object becomes a subclass of the current object.</span></span>

<span data-ttu-id="56160-134">`ppNewClass`에서 반환 되는 새 개체는 자동으로 현재 개체의 서브 클래스가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="56160-134">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="56160-135">이 동작은 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="56160-135">This behavior cannot be overridden.</span></span> <span data-ttu-id="56160-136">서브 클래스 (파생 클래스)를 만들 수 있는 다른 방법은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="56160-136">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="56160-137">요구 사항</span><span class="sxs-lookup"><span data-stu-id="56160-137">Requirements</span></span>  
 <span data-ttu-id="56160-138">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="56160-138">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56160-139">**헤더:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="56160-139">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="56160-140">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="56160-140">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56160-141">참조</span><span class="sxs-lookup"><span data-stu-id="56160-141">See also</span></span>

- [<span data-ttu-id="56160-142">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="56160-142">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
