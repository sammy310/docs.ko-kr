---
title: GetQualifierSet 함수 (관리 되지 않는 API 참조)
description: GetQualifierSet 함수는 클래스 또는 인스턴스의 한정자 집합을 검색 합니다.
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
ms.openlocfilehash: f9bb882a0f62499167b79bf3e6691d05e394720f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671345"
---
# <a name="getqualifierset-function"></a><span data-ttu-id="7ed89-103">GetQualifierSet 함수</span><span class="sxs-lookup"><span data-stu-id="7ed89-103">GetQualifierSet function</span></span>

<span data-ttu-id="7ed89-104">클래스 인스턴스 또는 클래스 정의에 대한 한정자 집합을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="7ed89-104">Retrieves the qualifier set for a class instance or a class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="7ed89-105">구문</span><span class="sxs-lookup"><span data-stu-id="7ed89-105">Syntax</span></span>  
  
```cpp  
HRESULT GetQualifierSet (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [out] IWbemQualifierSet  **ppQualSet
);
```  

## <a name="parameters"></a><span data-ttu-id="7ed89-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7ed89-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="7ed89-107">진행 이 매개 변수는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7ed89-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="7ed89-108">진행 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7ed89-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppQualSet`  
<span data-ttu-id="7ed89-109">제한이 클래스 개체의 한정자에 대 한 액세스를 허용 하는 인터페이스 포인터를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="7ed89-109">[out] Receives the interface pointer that allows access to the qualifiers of the class object.</span></span> <span data-ttu-id="7ed89-110">`ppQualSet`가 `null`이 될 수 없는 경우</span><span class="sxs-lookup"><span data-stu-id="7ed89-110">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="7ed89-111">오류가 발생 하면 새 개체가 반환 되지 않고 포인터가 수정 되지 않은 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ed89-111">If an error occurs, a new object is not returned, and the pointer is left unmodified.</span></span>

## <a name="return-value"></a><span data-ttu-id="7ed89-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="7ed89-112">Return value</span></span>

<span data-ttu-id="7ed89-113">이 함수에서 반환 되는 다음 값은 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ed89-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="7ed89-114">상수</span><span class="sxs-lookup"><span data-stu-id="7ed89-114">Constant</span></span>  |<span data-ttu-id="7ed89-115">값</span><span class="sxs-lookup"><span data-stu-id="7ed89-115">Value</span></span>  |<span data-ttu-id="7ed89-116">설명</span><span class="sxs-lookup"><span data-stu-id="7ed89-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="7ed89-117">0x80041001</span><span class="sxs-lookup"><span data-stu-id="7ed89-117">0x80041001</span></span> | <span data-ttu-id="7ed89-118">일반 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7ed89-118">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="7ed89-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="7ed89-119">0x80041002</span></span> | <span data-ttu-id="7ed89-120">지정 된 메서드가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7ed89-120">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="7ed89-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="7ed89-121">0x80041006</span></span> | <span data-ttu-id="7ed89-122">메모리가 부족 하 여 작업을 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7ed89-122">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="7ed89-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="7ed89-123">0x80041008</span></span> | <span data-ttu-id="7ed89-124">매개 `null` 변수가 인 경우</span><span class="sxs-lookup"><span data-stu-id="7ed89-124">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="7ed89-125">0</span><span class="sxs-lookup"><span data-stu-id="7ed89-125">0</span></span> | <span data-ttu-id="7ed89-126">함수 호출에 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7ed89-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="7ed89-127">설명</span><span class="sxs-lookup"><span data-stu-id="7ed89-127">Remarks</span></span>

<span data-ttu-id="7ed89-128">이 함수는 [IWbemClassObject:: GetQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset) 메서드에 대 한 호출을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="7ed89-128">This function wraps a call to the [IWbemClassObject::GetQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset) method.</span></span>

<span data-ttu-id="7ed89-129">[IWbemQualifierSet 포인터](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) 를 사용 하면 호출자가 이러한 한정자를 추가, 편집 또는 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ed89-129">The [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span> <span data-ttu-id="7ed89-130">이러한 추가, 편집 또는 삭제 된 한정자는 전체 인스턴스 또는 클래스 정의에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ed89-130">Such added, edited, or deleted qualifiers apply to the entire instance or class definition.</span></span>

## <a name="requirements"></a><span data-ttu-id="7ed89-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7ed89-131">Requirements</span></span>  

<span data-ttu-id="7ed89-132">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7ed89-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ed89-133">**헤더:** WMINet_Utils idl</span><span class="sxs-lookup"><span data-stu-id="7ed89-133">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="7ed89-134">**.NET Framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7ed89-134">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ed89-135">참조</span><span class="sxs-lookup"><span data-stu-id="7ed89-135">See also</span></span>

- [<span data-ttu-id="7ed89-136">WMI 및 성능 카운터(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="7ed89-136">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
