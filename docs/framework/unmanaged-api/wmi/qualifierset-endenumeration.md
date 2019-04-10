---
title: QualifierSet_EndEnumeration 함수 (관리 되지 않는 API 참조)
description: QualifierSet_EndEnumeration 함수 열거형을 종료합니다.
ms.date: 11/06/2017
api_name:
- QualifierSet_EndEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_EndEnumeration
helpviewer_keywords:
- QualifierSet_EndEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be2dfd6bb521dee14afd3728bdd9c446cb779e85
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59149229"
---
# <a name="qualifiersetendenumeration-function"></a><span data-ttu-id="609c1-103">QualifierSet_EndEnumeration 함수</span><span class="sxs-lookup"><span data-stu-id="609c1-103">QualifierSet_EndEnumeration function</span></span>
<span data-ttu-id="609c1-104">에 대 한 호출으로 시작 하는 열거형을 종료 합니다 [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="609c1-104">Terminates the enumeration begun with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="609c1-105">구문</span><span class="sxs-lookup"><span data-stu-id="609c1-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr
); 
```  

## <a name="parameters"></a><span data-ttu-id="609c1-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="609c1-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="609c1-107">[in] 이 매개 변수 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="609c1-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="609c1-108">[in] 에 대 한 포인터를 [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="609c1-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="609c1-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="609c1-109">Return value</span></span>

<span data-ttu-id="609c1-110">이 함수에 의해 반환 되는 다음 값에 정의 되어는 *WbemCli.h* 헤더 파일을 정의할 수는 상수로 코드에서:</span><span class="sxs-lookup"><span data-stu-id="609c1-110">The following value returned by this function is defined in the *WbemCli.h* header file, or you can define it as a constant in your code:</span></span>

|<span data-ttu-id="609c1-111">상수</span><span class="sxs-lookup"><span data-stu-id="609c1-111">Constant</span></span>  |<span data-ttu-id="609c1-112">값</span><span class="sxs-lookup"><span data-stu-id="609c1-112">Value</span></span>  |<span data-ttu-id="609c1-113">설명</span><span class="sxs-lookup"><span data-stu-id="609c1-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | <span data-ttu-id="609c1-114">0</span><span class="sxs-lookup"><span data-stu-id="609c1-114">0</span></span> | <span data-ttu-id="609c1-115">함수 호출이 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="609c1-115">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="609c1-116">설명</span><span class="sxs-lookup"><span data-stu-id="609c1-116">Remarks</span></span>

<span data-ttu-id="609c1-117">이 함수에 대 한 호출을 래핑하는 [IWbemQualifierSet::EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) 메서드.</span><span class="sxs-lookup"><span data-stu-id="609c1-117">This function wraps a call to the [IWbemQualifierSet::EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) method.</span></span>

<span data-ttu-id="609c1-118">이 호출은 것이 좋지만 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="609c1-118">This call is recommended, but not required.</span></span> <span data-ttu-id="609c1-119">열거형을 사용 하 여 연결 된 리소스를 즉시 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="609c1-119">It immediately releases resources associated with the enumeration.</span></span>

## <a name="requirements"></a><span data-ttu-id="609c1-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="609c1-120">Requirements</span></span>  

<span data-ttu-id="609c1-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="609c1-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="609c1-122">**헤더:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="609c1-122">**Header:** WMINet_Utils.idl</span></span>  
  
**<span data-ttu-id="609c1-123">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="609c1-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="609c1-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="609c1-124">See also</span></span>

- [<span data-ttu-id="609c1-125">WMI 및 성능 카운터(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="609c1-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
