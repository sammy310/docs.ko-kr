---
title: GetQualifierSet 함수(관리되지 않는 API 참조)
description: GetQualifierSet 함수는 클래스 또는 인스턴스에 대한 한정자 집합을 검색합니다.
ms.date: 11/06/2017
api_name:
- GetQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetQualifierSet
helpviewer_keywords:
- GetQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 368f0a13871bd48780fa30b370d37157d2724bb8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176775"
---
# <a name="getqualifierset-function"></a><span data-ttu-id="0f41b-103">GetQualifierSet 함수</span><span class="sxs-lookup"><span data-stu-id="0f41b-103">GetQualifierSet function</span></span>
<span data-ttu-id="0f41b-104">클래스 인스턴스 또는 클래스 정의에 대한 한정자 집합을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="0f41b-104">Retrieves the qualifier set for a class instance or a class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="0f41b-105">구문</span><span class="sxs-lookup"><span data-stu-id="0f41b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetQualifierSet (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [out] IWbemQualifierSet  **ppQualSet
);
```  

## <a name="parameters"></a><span data-ttu-id="0f41b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0f41b-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="0f41b-107">【인】 이 매개 변수는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f41b-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="0f41b-108">【인】 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0f41b-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppQualSet`  
<span data-ttu-id="0f41b-109">【아웃】 클래스 개체의 한정자에 액세스할 수 있는 인터페이스 포인터를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="0f41b-109">[out] Receives the interface pointer that allows access to the qualifiers of the class object.</span></span> <span data-ttu-id="0f41b-110">`ppQualSet`가 `null`이 될 수 없는 경우</span><span class="sxs-lookup"><span data-stu-id="0f41b-110">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="0f41b-111">오류가 발생하면 새 개체가 반환되지 않고 포인터가 수정되지 않은 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f41b-111">If an error occurs, a new object is not returned, and the pointer is left unmodified.</span></span>

## <a name="return-value"></a><span data-ttu-id="0f41b-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="0f41b-112">Return value</span></span>

<span data-ttu-id="0f41b-113">이 함수에서 반환되는 다음 값은 *WbemCli.h* 헤더 파일에 정의되거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f41b-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="0f41b-114">지속적임</span><span class="sxs-lookup"><span data-stu-id="0f41b-114">Constant</span></span>  |<span data-ttu-id="0f41b-115">값</span><span class="sxs-lookup"><span data-stu-id="0f41b-115">Value</span></span>  |<span data-ttu-id="0f41b-116">Description</span><span class="sxs-lookup"><span data-stu-id="0f41b-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="0f41b-117">0x80041001</span><span class="sxs-lookup"><span data-stu-id="0f41b-117">0x80041001</span></span> | <span data-ttu-id="0f41b-118">일반적인 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="0f41b-118">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="0f41b-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="0f41b-119">0x80041002</span></span> | <span data-ttu-id="0f41b-120">지정된 메서드가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f41b-120">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="0f41b-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="0f41b-121">0x80041006</span></span> | <span data-ttu-id="0f41b-122">메모리가 부족 하 여 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f41b-122">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="0f41b-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="0f41b-123">0x80041008</span></span> | <span data-ttu-id="0f41b-124">매개 변수는 `null`.</span><span class="sxs-lookup"><span data-stu-id="0f41b-124">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="0f41b-125">0</span><span class="sxs-lookup"><span data-stu-id="0f41b-125">0</span></span> | <span data-ttu-id="0f41b-126">함수 호출이 성공했습니다.</span><span class="sxs-lookup"><span data-stu-id="0f41b-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="0f41b-127">설명</span><span class="sxs-lookup"><span data-stu-id="0f41b-127">Remarks</span></span>

<span data-ttu-id="0f41b-128">이 함수는 [IWbemClassObject::GetQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset) 메서드에 대한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="0f41b-128">This function wraps a call to the [IWbemClassObject::GetQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset) method.</span></span>

<span data-ttu-id="0f41b-129">[IWbemQualifierSet 포인터를](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) 사용하면 호출자가 이러한 한정자를 추가, 편집 또는 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f41b-129">The [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span> <span data-ttu-id="0f41b-130">이러한 추가, 편집 또는 삭제된 한정자는 전체 인스턴스 또는 클래스 정의에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f41b-130">Such added, edited, or deleted qualifiers apply to the entire instance or class definition.</span></span>

## <a name="requirements"></a><span data-ttu-id="0f41b-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0f41b-131">Requirements</span></span>  
<span data-ttu-id="0f41b-132">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f41b-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f41b-133">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="0f41b-133">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="0f41b-134">**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0f41b-134">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f41b-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0f41b-135">See also</span></span>

- [<span data-ttu-id="0f41b-136">WMI 및 성능 카운터(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="0f41b-136">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
