---
title: ICorDebugClass::GetStaticFieldValue 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugClass.GetStaticFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass::GetStaticFieldValue
helpviewer_keywords:
- GetStaticFieldValue method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetStaticFieldValue method [.NET Framework debugging]
ms.assetid: 56e718b4-fabd-418b-a5b3-3cc33c745683
topic_type:
- apiref
ms.openlocfilehash: 867db3325f9b18b31f66429d01ea02be3603c0f6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125756"
---
# <a name="icordebugclassgetstaticfieldvalue-method"></a><span data-ttu-id="bbff2-102">ICorDebugClass::GetStaticFieldValue 메서드</span><span class="sxs-lookup"><span data-stu-id="bbff2-102">ICorDebugClass::GetStaticFieldValue Method</span></span>
<span data-ttu-id="bbff2-103">지정 된 정적 필드의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bbff2-103">Gets the value of the specified static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbff2-104">구문</span><span class="sxs-lookup"><span data-stu-id="bbff2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef         fieldDef,  
    [in]  ICorDebugFrame     *pFrame,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bbff2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bbff2-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="bbff2-106">진행 검색할 필드를 참조 하는 필드 `Def` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="bbff2-106">[in] A field `Def` token that references the field to be retrieved.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="bbff2-107">진행 스레드, 컨텍스트 또는 응용 프로그램 도메인 정적을 명확 하 게 구분 하는 데 사용할 프레임을 나타내는 ICorDebugFrame 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bbff2-107">[in] A pointer to an ICorDebugFrame object that represents the frame to be used to disambiguate among thread, context, or application domain statics.</span></span>  
  
 <span data-ttu-id="bbff2-108">정적 필드가 스레드, 컨텍스트 또는 응용 프로그램 도메인을 기준으로 하는 경우 프레임에 적절 한 값이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbff2-108">If the static field is relative to a thread, a context, or an application domain, the frame will determine the proper value.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="bbff2-109">제한이 정적 필드의 값을 나타내는 ICorDebugValue 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bbff2-109">[out] A pointer to the address of an ICorDebugValue object that represents the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bbff2-110">주의</span><span class="sxs-lookup"><span data-stu-id="bbff2-110">Remarks</span></span>  
 <span data-ttu-id="bbff2-111">매개 변수가 있는 형식의 경우 정적 필드의 값은 특정 인스턴스화를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbff2-111">For parameterized types, the value of a static field is relative to the particular instantiation.</span></span> <span data-ttu-id="bbff2-112">따라서 클래스 생성자가 <xref:System.Type>형식의 매개 변수를 사용 하는 경우 `ICorDebugClass::GetStaticFieldValue`대신 [ICorDebugType:: GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md) 를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbff2-112">Therefore, if the class constructor takes parameters of type <xref:System.Type>, call [ICorDebugType::GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md) instead of `ICorDebugClass::GetStaticFieldValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbff2-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bbff2-113">Requirements</span></span>  
 <span data-ttu-id="bbff2-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bbff2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbff2-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bbff2-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bbff2-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bbff2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bbff2-117">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbff2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
