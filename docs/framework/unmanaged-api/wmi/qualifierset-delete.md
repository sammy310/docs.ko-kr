---
title: QualifierSet_Delete 함수 (관리 되지 않는 API 참조)
description: QualifierSet_Delete 함수 이름별 한정자를 삭제합니다.
ms.date: 11/06/2017
api_name:
- QualifierSet_Delete
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Delete
helpviewer_keywords:
- QualifierSet_Delete function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 543cc63b3e2188c11a6a8bf1eaa846461375be99
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59180078"
---
# <a name="qualifiersetdelete-function"></a><span data-ttu-id="3bb6c-103">QualifierSet_Delete 함수</span><span class="sxs-lookup"><span data-stu-id="3bb6c-103">QualifierSet_Delete function</span></span>
<span data-ttu-id="3bb6c-104">지정된 한정자를 이름으로 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb6c-104">Deletes a specified qualifier by name.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="3bb6c-105">구문</span><span class="sxs-lookup"><span data-stu-id="3bb6c-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_Delete (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName
); 
```  

## <a name="parameters"></a><span data-ttu-id="3bb6c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3bb6c-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="3bb6c-107">[in] 이 매개 변수 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3bb6c-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="3bb6c-108">[in] 에 대 한 포인터를 [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="3bb6c-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`wszName`   
<span data-ttu-id="3bb6c-109">[in] 삭제 하는 데 사용할 한정자의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3bb6c-109">[in] The name of the qualifier to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="3bb6c-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="3bb6c-110">Return value</span></span>

<span data-ttu-id="3bb6c-111">이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:</span><span class="sxs-lookup"><span data-stu-id="3bb6c-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="3bb6c-112">상수</span><span class="sxs-lookup"><span data-stu-id="3bb6c-112">Constant</span></span>  |<span data-ttu-id="3bb6c-113">값</span><span class="sxs-lookup"><span data-stu-id="3bb6c-113">Value</span></span>  |<span data-ttu-id="3bb6c-114">설명</span><span class="sxs-lookup"><span data-stu-id="3bb6c-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="3bb6c-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="3bb6c-115">0x80041008</span></span> | <span data-ttu-id="3bb6c-116">`wszName` 매개 변수가 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3bb6c-116">The `wszName` parameter is not valid.</span></span> |
|`WBEM_E_INVALID_OPERATION` | <span data-ttu-id="3bb6c-117">0x80041016</span><span class="sxs-lookup"><span data-stu-id="3bb6c-117">0x80041016</span></span> | <span data-ttu-id="3bb6c-118">이 한정자를 삭제 하는 중 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3bb6c-118">Deleting this qualifier is illegal.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="3bb6c-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="3bb6c-119">0x80041002</span></span> | <span data-ttu-id="3bb6c-120">지정된 된 한정자를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3bb6c-120">The specified qualifier was not found.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="3bb6c-121">0</span><span class="sxs-lookup"><span data-stu-id="3bb6c-121">0</span></span> | <span data-ttu-id="3bb6c-122">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3bb6c-122">The function call was successful.</span></span>  |
| `WBEM_S_RESET_TO_DEFAULT` | <span data-ttu-id="3bb6c-123">0x40002</span><span class="sxs-lookup"><span data-stu-id="3bb6c-123">0x40002</span></span> | <span data-ttu-id="3bb6c-124">로컬 재정의 삭제 하 고 부모 개체의 원래 한정자가 범위를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb6c-124">The local override was deleted and the original qualifier from the parent object has resumed scope.</span></span> |

## <a name="remarks"></a><span data-ttu-id="3bb6c-125">설명</span><span class="sxs-lookup"><span data-stu-id="3bb6c-125">Remarks</span></span>

<span data-ttu-id="3bb6c-126">이 함수에 대 한 호출을 래핑하는 [IWbemQualifierSet::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete) 메서드.</span><span class="sxs-lookup"><span data-stu-id="3bb6c-126">This function wraps a call to the [IWbemQualifierSet::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete) method.</span></span>

<span data-ttu-id="3bb6c-127">한정자 전파 규칙으로 인해 특정 한정자 수 다른 개체 로부터 상속 되었으며 단순히 인스턴스를 현재 클래스에서 재정의 된 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb6c-127">Due to qualifier propagation rules, a particular qualifier may have been inherited from another object and merely overridden in the current class or instance.</span></span> <span data-ttu-id="3bb6c-128">이 경우에 `QualifierSet_Delete` 메서드 다시 원래 상속 된 값으로 한정자를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb6c-128">In this case, the `QualifierSet_Delete` method resets the qualifier to its original inherited value.</span></span> <span data-ttu-id="3bb6c-129">함수에는 경우 상태 코드를 반환 합니다 `WBEM_S_RESET_TO_DEFAULT`합니다.</span><span class="sxs-lookup"><span data-stu-id="3bb6c-129">The function in this case returns the status code `WBEM_S_RESET_TO_DEFAULT`.</span></span>

## <a name="requirements"></a><span data-ttu-id="3bb6c-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3bb6c-130">Requirements</span></span>  
 <span data-ttu-id="3bb6c-131">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3bb6c-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bb6c-132">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="3bb6c-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="3bb6c-133">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3bb6c-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bb6c-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="3bb6c-134">See also</span></span>

- [<span data-ttu-id="3bb6c-135">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="3bb6c-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
