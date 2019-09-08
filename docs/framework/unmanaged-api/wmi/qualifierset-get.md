---
title: QualifierSet_Get 함수 (관리 되지 않는 API 참조)
description: QualifierSet_Get 함수는 명명 된 한정자를 가져옵니다.
ms.date: 11/06/2017
api_name:
- QualifierSet_Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Get
helpviewer_keywords:
- QualifierSet_Get function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 751694985248346187eff016ef7a4a8054cb1212
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798306"
---
# <a name="qualifierset_get-function"></a><span data-ttu-id="37516-103">QualifierSet_Get 함수</span><span class="sxs-lookup"><span data-stu-id="37516-103">QualifierSet_Get function</span></span>
<span data-ttu-id="37516-104">지정한 명명된 한정자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="37516-104">Gets the specified named qualifier.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="37516-105">구문</span><span class="sxs-lookup"><span data-stu-id="37516-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_Get (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName,
   [in] LONG                 lFlags,
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor                 
); 
```  

## <a name="parameters"></a><span data-ttu-id="37516-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="37516-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="37516-107">진행 이 매개 변수는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37516-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="37516-108">진행 [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="37516-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`wszName`   
<span data-ttu-id="37516-109">진행 해당 값이 요청 된 한정자의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="37516-109">[in] The name of the qualifier whose value is requested.</span></span>

`lFlags`   
<span data-ttu-id="37516-110">[in] 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37516-110">[in] Reserved.</span></span> <span data-ttu-id="37516-111">이 매개 변수는 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="37516-111">This parameter must be 0.</span></span>

`pVal`   
<span data-ttu-id="37516-112">제한이 성공 하면 한정자의 올바른 형식 및 값입니다.</span><span class="sxs-lookup"><span data-stu-id="37516-112">[out] When successful, the correct type and value for the qualifier.</span></span> <span data-ttu-id="37516-113">함수가 실패 `VARIANT` 하면에서 가리키는가 `pVal` 수정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37516-113">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="37516-114">이 매개 변수가 `null`이면 매개 변수는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37516-114">If this parameter is `null`, the parameter is ignored.</span></span>

`plFlavor`   
<span data-ttu-id="37516-115">제한이 요청 된 한정자에 대 한 한정자 버전 비트를 받는 LONG에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="37516-115">[out] A pointer to a LONG that receives the qualifier flavor bits for the requested qualifier.</span></span> <span data-ttu-id="37516-116">버전 정보를 원하지 않는 경우이 매개 변수는 일 `null`수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37516-116">If flavor information is not desired, this parameter can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="37516-117">반환 값</span><span class="sxs-lookup"><span data-stu-id="37516-117">Return value</span></span>

<span data-ttu-id="37516-118">이 함수에서 반환 되는 다음 값은 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37516-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="37516-119">상수</span><span class="sxs-lookup"><span data-stu-id="37516-119">Constant</span></span>  |<span data-ttu-id="37516-120">값</span><span class="sxs-lookup"><span data-stu-id="37516-120">Value</span></span>  |<span data-ttu-id="37516-121">Description</span><span class="sxs-lookup"><span data-stu-id="37516-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="37516-122">0x80041008</span><span class="sxs-lookup"><span data-stu-id="37516-122">0x80041008</span></span> | <span data-ttu-id="37516-123">매개 변수가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="37516-123">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="37516-124">0x80041002</span><span class="sxs-lookup"><span data-stu-id="37516-124">0x80041002</span></span> | <span data-ttu-id="37516-125">지정한 한정자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37516-125">The specified qualifier does not exist.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="37516-126">0</span><span class="sxs-lookup"><span data-stu-id="37516-126">0</span></span> | <span data-ttu-id="37516-127">함수 호출에 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="37516-127">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="37516-128">설명</span><span class="sxs-lookup"><span data-stu-id="37516-128">Remarks</span></span>

<span data-ttu-id="37516-129">이 함수는 [IWbemQualifierSet:: Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get) 메서드에 대 한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="37516-129">This function wraps a call to the [IWbemQualifierSet::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="37516-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="37516-130">Requirements</span></span>  
 <span data-ttu-id="37516-131">**플랫폼** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="37516-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37516-132">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="37516-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="37516-133">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="37516-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37516-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="37516-134">See also</span></span>

- [<span data-ttu-id="37516-135">WMI 및 성능 카운터 (관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="37516-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
