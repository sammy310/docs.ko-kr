---
title: ICorDebugNativeFrame::GetLocalDoubleRegisterValue 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalDoubleRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalDoubleRegisterValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalDoubleRegisterValue method [.NET Framework debugging]
- GetLocalDoubleRegisterValue method [.NET Framework debugging]
ms.assetid: 1f838215-ac8a-434f-8ce6-03021d3098d9
topic_type:
- apiref
ms.openlocfilehash: a45061b6a3105565fdbb36173731b3c3dfe5aa4f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137292"
---
# <a name="icordebugnativeframegetlocaldoubleregistervalue-method"></a><span data-ttu-id="31261-102">ICorDebugNativeFrame::GetLocalDoubleRegisterValue 메서드</span><span class="sxs-lookup"><span data-stu-id="31261-102">ICorDebugNativeFrame::GetLocalDoubleRegisterValue Method</span></span>
<span data-ttu-id="31261-103">이 네이티브 프레임의 지정 된 두 레지스터에 저장 된 인수 또는 지역 변수의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="31261-103">Gets the value of an argument or local variable that is stored in the two specified registers for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31261-104">구문</span><span class="sxs-lookup"><span data-stu-id="31261-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalDoubleRegisterValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CorDebugRegister   lowWordReg,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31261-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="31261-105">Parameters</span></span>  
 `highWordReg`  
 <span data-ttu-id="31261-106">진행 값의 상위 단어가 포함 된 레지스터를 지정 하는 "CorDebugRegister" 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="31261-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the high word of the value.</span></span>  
  
 `lowWordReg`  
 <span data-ttu-id="31261-107">진행 값의 하위 단어를 포함 하는 레지스터를 지정 하는 `CorDebugRegister` 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="31261-107">[in] A value of the `CorDebugRegister` enumeration that specifies the register containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="31261-108">진행 `pvSigBlob` 매개 변수에서 참조 하는 이진 메타 데이터 서명의 크기를 지정 하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="31261-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="31261-109">진행 값 형식의 이진 메타 데이터 서명을 가리키는 `PCCOR_SIGNATURE` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="31261-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="31261-110">제한이 지정 된 레지스터에 저장 된 검색 된 값을 나타내는 "ICorDebugValue" 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="31261-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified registers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="31261-111">주의</span><span class="sxs-lookup"><span data-stu-id="31261-111">Remarks</span></span>  
 <span data-ttu-id="31261-112">네이티브 프레임 또는 JIT (just-in-time) 컴파일된 프레임에서 `GetLocalDoubleRegisterValue` 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31261-112">The `GetLocalDoubleRegisterValue` method can be used either in a native frame or a just-in-time (JIT)-compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31261-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="31261-113">Requirements</span></span>  
 <span data-ttu-id="31261-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="31261-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31261-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="31261-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="31261-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="31261-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="31261-117">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31261-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31261-118">참조</span><span class="sxs-lookup"><span data-stu-id="31261-118">See also</span></span>
