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
ms.openlocfilehash: 4c4bfe6a797fc1476ff53a8f2db4f80debc41f6b
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212440"
---
# <a name="icordebugnativeframegetlocalmemoryvalue-method"></a><span data-ttu-id="2f966-102">ICorDebugNativeFrame::GetLocalMemoryValue 메서드</span><span class="sxs-lookup"><span data-stu-id="2f966-102">ICorDebugNativeFrame::GetLocalMemoryValue Method</span></span>
<span data-ttu-id="2f966-103">이 네이티브 프레임의 지정 된 메모리 위치에 저장 된 인수 또는 지역 변수의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2f966-103">Gets the value of an argument or local variable that is stored in the specified memory location for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f966-104">구문</span><span class="sxs-lookup"><span data-stu-id="2f966-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalMemoryValue (  
    [in]  CORDB_ADDRESS      address,  
    [in]  ULONG              cbSigBlob,  
    [in]  PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f966-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2f966-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="2f966-106">진행 `CORDB_ADDRESS`값을 포함 하는 메모리 위치를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2f966-106">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="2f966-107">진행 매개 변수에서 참조 하는 이진 메타 데이터 시그니처의 크기를 지정 하는 정수입니다 `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="2f966-107">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="2f966-108">진행 `PCCOR_SIGNATURE`값 형식의 이진 메타 데이터 서명을 가리키는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2f966-108">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="2f966-109">제한이 지정 된 메모리 위치에 저장 된 검색 된 값을 나타내는 "ICorDebugValue" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2f966-109">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f966-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2f966-110">Requirements</span></span>  
 <span data-ttu-id="2f966-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2f966-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f966-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2f966-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2f966-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f966-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f966-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f966-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f966-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2f966-115">See also</span></span>
