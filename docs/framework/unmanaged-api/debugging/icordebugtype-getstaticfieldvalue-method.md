---
title: ICorDebugType::GetStaticFieldValue 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetStaticFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetStaticFieldValue
helpviewer_keywords:
- GetStaticFieldValue method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::GetStaticFieldValue method [.NET Framework debugging]
ms.assetid: 62eb5d55-53ee-4fb3-8d47-7b6c96808f9e
topic_type:
- apiref
ms.openlocfilehash: 83ac91133b226e2ac263356941c3fc3288355e7e
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379930"
---
# <a name="icordebugtypegetstaticfieldvalue-method"></a><span data-ttu-id="a077d-102">ICorDebugType::GetStaticFieldValue 메서드</span><span class="sxs-lookup"><span data-stu-id="a077d-102">ICorDebugType::GetStaticFieldValue Method</span></span>
<span data-ttu-id="a077d-103">지정 된 스택 프레임에서 지정 된 필드 토큰이 참조 하는 정적 필드의 값을 포함 하는 ICorDebugValue 개체에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a077d-103">Gets an interface pointer to an ICorDebugValue object that contains the value of the static field referenced by the specified field token in the specified stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a077d-104">구문</span><span class="sxs-lookup"><span data-stu-id="a077d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef        fieldDef,  
    [in]  ICorDebugFrame    *pFrame,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a077d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a077d-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="a077d-106">진행 `mdFieldDef`정적 필드를 지정 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="a077d-106">[in] An `mdFieldDef` token that specifies the static field.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="a077d-107">진행 스택 프레임을 나타내는 ICorDebugFrame에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a077d-107">[in] A pointer to an ICorDebugFrame that represents the stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="a077d-108">제한이 `ICorDebugValue`정적 필드의 값을 포함 하는의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a077d-108">[out] A pointer to the address of an `ICorDebugValue` that contains the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a077d-109">설명</span><span class="sxs-lookup"><span data-stu-id="a077d-109">Remarks</span></span>  
 <span data-ttu-id="a077d-110">`GetStaticFieldValue` [ICorDebugType:: GetType](icordebugtype-gettype-method.md) 메서드에 표시 된 대로 형식이 ELEMENT_TYPE_CLASS 또는 ELEMENT_TYPE_VALUETYPE 인 경우에만 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a077d-110">The `GetStaticFieldValue` method may be used only if the type is ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, as indicated by the [ICorDebugType::GetType](icordebugtype-gettype-method.md) method.</span></span>  
  
 <span data-ttu-id="a077d-111">제네릭이 아닌 형식의 경우에서 수행 하는 작업은 `GetStaticFieldValue` [ICorDebugType:: getclass](icordebugtype-getclass-method.md)에 의해 반환 되는 ICorDebugClass 개체에 대해 [ICorDebugClass:: GetStaticFieldValue](icordebugclass-getstaticfieldvalue-method.md) 를 호출 하는 것과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="a077d-111">For non-generic types, the operation performed by `GetStaticFieldValue` is identical to calling [ICorDebugClass::GetStaticFieldValue](icordebugclass-getstaticfieldvalue-method.md) on the ICorDebugClass object that is returned by [ICorDebugType::GetClass](icordebugtype-getclass-method.md).</span></span>  
  
 <span data-ttu-id="a077d-112">제네릭 형식의 경우 정적 필드 값은 특정 인스턴스화를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a077d-112">For generic types, a static field value will be relative to a particular instantiation.</span></span> <span data-ttu-id="a077d-113">또한 정적 필드가 스레드, 컨텍스트 또는 응용 프로그램 도메인에 대 한 상대 값일 수 있는 경우 스택 프레임은 디버거가 적절 한 값을 결정 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a077d-113">Also, if the static field could possibly be relative to a thread, a context, or an application domain, then the stack frame will help the debugger determine the proper value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a077d-114">설명</span><span class="sxs-lookup"><span data-stu-id="a077d-114">Remarks</span></span>  
 <span data-ttu-id="a077d-115">`GetStaticFieldValue`에 대 한 호출이 `ICorDebugType::GetType` ELEMENT_TYPE_CLASS 또는 ELEMENT_TYPE_VALUETYPE의 값을 반환 하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a077d-115">`GetStaticFieldValue` can be used only when a call to `ICorDebugType::GetType` returns a value of ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a077d-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a077d-116">Requirements</span></span>  
 <span data-ttu-id="a077d-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a077d-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a077d-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a077d-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a077d-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a077d-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a077d-120">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a077d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
