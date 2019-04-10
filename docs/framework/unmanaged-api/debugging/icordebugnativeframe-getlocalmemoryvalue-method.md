---
title: ICorDebugNativeFrame::GetLocalMemoryValue 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalMemoryValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalMemoryValue
helpviewer_keywords:
- GetLocalMemoryValue method [.NET Framework debugging]
- ICorDebugNativeFrame::GetLocalMemoryValue method [.NET Framework debugging]
ms.assetid: b600b3a2-9908-42d8-8093-ab6f39e9a2c9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6c44f3e369ac64773811a6aea74756783dedd2fc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59209465"
---
# <a name="icordebugnativeframegetlocalmemoryvalue-method"></a><span data-ttu-id="1e894-102">ICorDebugNativeFrame::GetLocalMemoryValue 메서드</span><span class="sxs-lookup"><span data-stu-id="1e894-102">ICorDebugNativeFrame::GetLocalMemoryValue Method</span></span>
<span data-ttu-id="1e894-103">네이티브 프레임에 대 한 지정 된 메모리 위치에 저장 된 로컬 변수 또는 인수의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1e894-103">Gets the value of an argument or local variable that is stored in the specified memory location for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e894-104">구문</span><span class="sxs-lookup"><span data-stu-id="1e894-104">Syntax</span></span>  
  
```  
HRESULT GetLocalMemoryValue (  
    [in]  CORDB_ADDRESS      address,  
    [in]  ULONG              cbSigBlob,  
    [in]  PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e894-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1e894-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="1e894-106">[in] `CORDB_ADDRESS` 값이 포함 된 메모리 위치를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1e894-106">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="1e894-107">[in] 참조 하는 이진 메타 데이터 서명의 크기를 지정 하는 정수를 `pvSigBlob` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="1e894-107">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="1e894-108">[in] `PCCOR_SIGNATURE` 이진 메타 데이터 서명의 값의 형식 가리키는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1e894-108">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="1e894-109">[out] 지정된 된 메모리 위치에 저장 된 검색된 된 값을 나타내는 "ICorDebugValue" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1e894-109">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e894-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1e894-110">Requirements</span></span>  
 <span data-ttu-id="1e894-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1e894-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e894-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1e894-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1e894-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1e894-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="1e894-114">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="1e894-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1e894-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="1e894-115">See also</span></span>
