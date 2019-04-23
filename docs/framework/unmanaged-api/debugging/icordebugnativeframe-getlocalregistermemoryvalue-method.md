---
title: ICorDebugNativeFrame::GetLocalRegisterMemoryValue 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalRegisterMemoryValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalRegisterMemoryValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalRegisterMemoryValue method [.NET Framework debugging]
- GetLocalRegisterMemoryValue method [.NET Framework debugging]
ms.assetid: d350f69d-9aff-4f5a-8301-daea22dee2da
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 26cd30be591c4167fa6a6e4d19ba9d1c909c6428
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59145771"
---
# <a name="icordebugnativeframegetlocalregistermemoryvalue-method"></a><span data-ttu-id="8aec5-102">ICorDebugNativeFrame::GetLocalRegisterMemoryValue 메서드</span><span class="sxs-lookup"><span data-stu-id="8aec5-102">ICorDebugNativeFrame::GetLocalRegisterMemoryValue Method</span></span>
<span data-ttu-id="8aec5-103">하위 워드 및 높은 word 메모리 위치에 저장 됩니다 및 네이티브 프레임에 대 한 레지스터를 각각 지정 된 지역 변수 또는 인수의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8aec5-103">Gets the value of an argument or local variable, of which the low word and high word are stored in the memory location and specified register, respectively, for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8aec5-104">구문</span><span class="sxs-lookup"><span data-stu-id="8aec5-104">Syntax</span></span>  
  
```  
HRESULT GetLocalRegisterMemoryValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CORDB_ADDRESS      lowWordAddress,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8aec5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8aec5-105">Parameters</span></span>  
 `highWordReg`  
 <span data-ttu-id="8aec5-106">[in] 값의 상위 단어를 포함 하는 레지스터를 지정 하는 "CorDebugRegister" 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8aec5-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the high word of the value.</span></span>  
  
 `lowWordAddress`  
 <span data-ttu-id="8aec5-107">[in] `CORDB_ADDRESS` 값의 낮은 단어를 포함 하는 메모리 위치를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8aec5-107">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="8aec5-108">[in] 참조 하는 이진 메타 데이터 서명의 크기를 지정 하는 정수를 `pvSigBlob` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="8aec5-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="8aec5-109">[in] `PCCOR_SIGNATURE` 이진 메타 데이터 서명의 값의 형식 가리키는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8aec5-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="8aec5-110">[out] 지정된 된 등록 및 메모리 위치에 저장 된 검색된 된 값을 나타내는 "ICorDebugValue" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8aec5-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register and memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8aec5-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8aec5-111">Requirements</span></span>  
 <span data-ttu-id="8aec5-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8aec5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8aec5-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8aec5-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8aec5-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8aec5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8aec5-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8aec5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8aec5-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="8aec5-116">See also</span></span>
