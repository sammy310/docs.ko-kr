---
title: SpawnDerivedClass 함수 (관리 되지 않는 API 참조)
description: SpawnDerivedClass 함수 개체에서 파생 되는 새 개체를 만듭니다.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 81f4d5219865bf7f7c9e6d284d74d0c249729dfc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59194424"
---
# <a name="spawnderivedclass-function"></a><span data-ttu-id="f26b0-103">SpawnDerivedClass 함수</span><span class="sxs-lookup"><span data-stu-id="f26b0-103">SpawnDerivedClass function</span></span>
<span data-ttu-id="f26b0-104">지정된 개체에서 새로 파생된 클래스 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f26b0-104">Creates a newly derived class object from a specified object.</span></span>    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="f26b0-105">구문</span><span class="sxs-lookup"><span data-stu-id="f26b0-105">Syntax</span></span>  
  
```  
HRESULT SpawnDerivedClass (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewClass); 
```  

## <a name="parameters"></a><span data-ttu-id="f26b0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f26b0-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="f26b0-107">[in] 이 매개 변수 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f26b0-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="f26b0-108">[in] 에 대 한 포인터를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="f26b0-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="f26b0-109">[in] 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f26b0-109">[in] Reserved.</span></span> <span data-ttu-id="f26b0-110">이 매개 변수는 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f26b0-110">This parameter must be 0.</span></span>

`ppNewClass`  
<span data-ttu-id="f26b0-111">[out] 새 클래스 정의 개체에 대 한 포인터를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="f26b0-111">[out] Receives the pointer to the new class definition object.</span></span> <span data-ttu-id="f26b0-112">오류가 발생 하는 새 개체가 없는 경우 반환 및 `ppNewClass` 왼쪽 수정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f26b0-112">If an error occurs, a new object is not returned, and `ppNewClass` is left unmodified.</span></span> <span data-ttu-id="f26b0-113">해당 값이 될 수 없습니다 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="f26b0-113">Its value cannot be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="f26b0-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="f26b0-114">Return value</span></span>

<span data-ttu-id="f26b0-115">이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="f26b0-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="f26b0-116">상수</span><span class="sxs-lookup"><span data-stu-id="f26b0-116">Constant</span></span>  |<span data-ttu-id="f26b0-117">값</span><span class="sxs-lookup"><span data-stu-id="f26b0-117">Value</span></span>  |<span data-ttu-id="f26b0-118">설명</span><span class="sxs-lookup"><span data-stu-id="f26b0-118">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="f26b0-119">0x80041001</span><span class="sxs-lookup"><span data-stu-id="f26b0-119">0x80041001</span></span> | <span data-ttu-id="f26b0-120">일반 오류가 발생이 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f26b0-120">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_OPERATION` | <span data-ttu-id="f26b0-121">0x80041016</span><span class="sxs-lookup"><span data-stu-id="f26b0-121">0x80041016</span></span> | <span data-ttu-id="f26b0-122">클래스는 인스턴스를 생성 하는 등 잘못 된 작업 요청 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f26b0-122">An invalid operation, such as spawning a class from an instance, was requested.</span></span> |
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="f26b0-123">완전히 원본 클래스 정의 되었거나 새 파생된 클래스는 허용 되지 않습니다 있도록 Windows 관리를 사용 하 여 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f26b0-123">The source class was not completely defined or registered with Windows Management, so a new derived class is not permitted.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="f26b0-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="f26b0-124">0x80041006</span></span> | <span data-ttu-id="f26b0-125">메모리가 부족 하 여 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f26b0-125">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="f26b0-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="f26b0-126">0x80041008</span></span> | `ppNewClass` <span data-ttu-id="f26b0-127">`null`합니다.</span><span class="sxs-lookup"><span data-stu-id="f26b0-127">is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="f26b0-128">0</span><span class="sxs-lookup"><span data-stu-id="f26b0-128">0</span></span> | <span data-ttu-id="f26b0-129">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f26b0-129">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="f26b0-130">설명</span><span class="sxs-lookup"><span data-stu-id="f26b0-130">Remarks</span></span>

<span data-ttu-id="f26b0-131">이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::SpawnDerivedClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) 메서드.</span><span class="sxs-lookup"><span data-stu-id="f26b0-131">This function wraps a call to the [IWbemClassObject::SpawnDerivedClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) method.</span></span>

`ptr` <span data-ttu-id="f26b0-132">생성 된 개체의 부모 클래스가 되는 클래스 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f26b0-132">must be a class definition that becomes the parent class of the spawned object.</span></span> <span data-ttu-id="f26b0-133">반환 된 개체가 현재 개체의 하위 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f26b0-133">The returned object becomes a subclass of the current object.</span></span>

<span data-ttu-id="f26b0-134">반환 되는 새 개체 `ppNewClass` 현재 개체의 하위 클래스는 자동으로 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f26b0-134">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="f26b0-135">이 동작을 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f26b0-135">This behavior cannot be overridden.</span></span> <span data-ttu-id="f26b0-136">서브 클래스 (파생된 클래스)을 만들 수 있는 다른 메서드가 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="f26b0-136">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="f26b0-137">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f26b0-137">Requirements</span></span>  
 <span data-ttu-id="f26b0-138">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f26b0-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f26b0-139">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="f26b0-139">**Header:** WMINet_Utils.idl</span></span>  
  
 **<span data-ttu-id="f26b0-140">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="f26b0-140">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f26b0-141">참고자료</span><span class="sxs-lookup"><span data-stu-id="f26b0-141">See also</span></span>

- [<span data-ttu-id="f26b0-142">WMI 및 성능 카운터(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="f26b0-142">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
