---
description: '자세히 알아보기: ICorDebugNativeFrame:: GetLocalRegisterValue 메서드'
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
ms.openlocfilehash: ae21134db11c4d0449ed5f6d583f435a259b83fe
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729148"
---
# <a name="icordebugnativeframegetlocalregistervalue-method"></a><span data-ttu-id="d53a2-103">ICorDebugNativeFrame::GetLocalRegisterValue 메서드</span><span class="sxs-lookup"><span data-stu-id="d53a2-103">ICorDebugNativeFrame::GetLocalRegisterValue Method</span></span>

<span data-ttu-id="d53a2-104">이 네이티브 프레임의 지정 된 레지스터에 저장 된 인수 또는 지역 변수의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d53a2-104">Gets the value of an argument or local variable that is stored in the specified register for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d53a2-105">구문</span><span class="sxs-lookup"><span data-stu-id="d53a2-105">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalRegisterValue (  
    [in]  CorDebugRegister   reg,  
    [in]  ULONG              cbSigBlob,  
    [in]  PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d53a2-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d53a2-106">Parameters</span></span>  

 `reg`  
 <span data-ttu-id="d53a2-107">진행 값을 포함 하는 레지스터를 지정 하는 "CorDebugRegister" 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d53a2-107">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="d53a2-108">진행 매개 변수에서 참조 하는 이진 메타 데이터 시그니처의 크기를 지정 하는 정수입니다 `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="d53a2-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="d53a2-109">진행 `PCCOR_SIGNATURE` 값 형식의 이진 메타 데이터 서명을 가리키는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d53a2-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="d53a2-110">제한이 지정 된 레지스터에 저장 된 검색 된 값을 나타내는 "ICorDebugValue" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d53a2-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d53a2-111">설명</span><span class="sxs-lookup"><span data-stu-id="d53a2-111">Remarks</span></span>  

 <span data-ttu-id="d53a2-112">`GetLocalRegisterValue`메서드는 네이티브 프레임 또는 JIT (just-in-time) 컴파일된 프레임에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d53a2-112">The `GetLocalRegisterValue` method can be used either in a native frame or a just-in-time (JIT)-compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d53a2-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d53a2-113">Requirements</span></span>  

 <span data-ttu-id="d53a2-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d53a2-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d53a2-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d53a2-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d53a2-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d53a2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d53a2-117">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d53a2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d53a2-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d53a2-118">See also</span></span>
