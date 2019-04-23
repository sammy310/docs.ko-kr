---
title: ICorDebugNativeFrame::GetLocalRegisterValue 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalRegisterValue
helpviewer_keywords:
- GetLocalRegisterValue method [.NET Framework debugging]
- ICorDebugNativeFrame::GetLocalRegisterValue method [.NET Framework debugging]
ms.assetid: 5ccb74f3-f891-430c-b70a-e370624edde2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f53c8290271391e52176f8364b592ce6b46faf71
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59195945"
---
# <a name="icordebugnativeframegetlocalregistervalue-method"></a><span data-ttu-id="daf6f-102">ICorDebugNativeFrame::GetLocalRegisterValue 메서드</span><span class="sxs-lookup"><span data-stu-id="daf6f-102">ICorDebugNativeFrame::GetLocalRegisterValue Method</span></span>
<span data-ttu-id="daf6f-103">네이티브 프레임에 대 한 지정된 된 레지스터에 저장 된 로컬 변수 또는 인수의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="daf6f-103">Gets the value of an argument or local variable that is stored in the specified register for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="daf6f-104">구문</span><span class="sxs-lookup"><span data-stu-id="daf6f-104">Syntax</span></span>  
  
```  
HRESULT GetLocalRegisterValue (  
    [in]  CorDebugRegister   reg,  
    [in]  ULONG              cbSigBlob,  
    [in]  PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="daf6f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="daf6f-105">Parameters</span></span>  
 `reg`  
 <span data-ttu-id="daf6f-106">[in] 값을 포함 하는 레지스터를 지정 하는 "CorDebugRegister" 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="daf6f-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="daf6f-107">[in] 참조 하는 이진 메타 데이터 서명의 크기를 지정 하는 정수를 `pvSigBlob` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="daf6f-107">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="daf6f-108">[in] `PCCOR_SIGNATURE` 이진 메타 데이터 서명의 값의 형식 가리키는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="daf6f-108">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="daf6f-109">[out] 지정된 된 레지스터에 저장 된 검색된 된 값을 나타내는 "ICorDebugValue" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="daf6f-109">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="daf6f-110">설명</span><span class="sxs-lookup"><span data-stu-id="daf6f-110">Remarks</span></span>  
 <span data-ttu-id="daf6f-111">`GetLocalRegisterValue` 네이티브 프레임이 또는-just-in-time (JIT) 메서드를 사용할 수 있습니다-프레임 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="daf6f-111">The `GetLocalRegisterValue` method can be used either in a native frame or a just-in-time (JIT)-compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="daf6f-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="daf6f-112">Requirements</span></span>  
 <span data-ttu-id="daf6f-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="daf6f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="daf6f-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="daf6f-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="daf6f-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="daf6f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="daf6f-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="daf6f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daf6f-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="daf6f-117">See also</span></span>
