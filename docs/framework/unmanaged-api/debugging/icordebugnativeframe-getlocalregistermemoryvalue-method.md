---
description: '자세히 알아보기: ICorDebugNativeFrame:: GetLocalRegisterMemoryValue 메서드'
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
ms.openlocfilehash: 36cf4d38c65e233a8be91a1e2aeca01ea009f340
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729187"
---
# <a name="icordebugnativeframegetlocalregistermemoryvalue-method"></a><span data-ttu-id="8c01a-103">ICorDebugNativeFrame::GetLocalRegisterMemoryValue 메서드</span><span class="sxs-lookup"><span data-stu-id="8c01a-103">ICorDebugNativeFrame::GetLocalRegisterMemoryValue Method</span></span>

<span data-ttu-id="8c01a-104">이 네이티브 프레임에 대해 하위 단어와 상위 단어가 각각 메모리 위치 및 지정 된 레지스터에 저장 되는 인수 또는 지역 변수의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8c01a-104">Gets the value of an argument or local variable, of which the low word and high word are stored in the memory location and specified register, respectively, for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c01a-105">구문</span><span class="sxs-lookup"><span data-stu-id="8c01a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalRegisterMemoryValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CORDB_ADDRESS      lowWordAddress,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c01a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8c01a-106">Parameters</span></span>  

 `highWordReg`  
 <span data-ttu-id="8c01a-107">진행 값의 상위 단어가 포함 된 레지스터를 지정 하는 "CorDebugRegister" 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8c01a-107">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the high word of the value.</span></span>  
  
 `lowWordAddress`  
 <span data-ttu-id="8c01a-108">진행 `CORDB_ADDRESS` 값의 하위 단어를 포함 하는 메모리 위치를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8c01a-108">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="8c01a-109">진행 매개 변수에서 참조 하는 이진 메타 데이터 시그니처의 크기를 지정 하는 정수입니다 `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="8c01a-109">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="8c01a-110">진행 `PCCOR_SIGNATURE` 값 형식의 이진 메타 데이터 서명을 가리키는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8c01a-110">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="8c01a-111">제한이 지정 된 레지스터 및 메모리 위치에 저장 된 검색 된 값을 나타내는 "ICorDebugValue" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8c01a-111">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register and memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c01a-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8c01a-112">Requirements</span></span>  

 <span data-ttu-id="8c01a-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8c01a-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c01a-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8c01a-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8c01a-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c01a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c01a-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c01a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c01a-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8c01a-117">See also</span></span>
