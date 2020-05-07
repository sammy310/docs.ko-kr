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
ms.openlocfilehash: d4a254853256e1a1440f5588418b94e39eabcc9a
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894103"
---
# <a name="icordebugclassgetstaticfieldvalue-method"></a><span data-ttu-id="77e7e-102">ICorDebugClass::GetStaticFieldValue 메서드</span><span class="sxs-lookup"><span data-stu-id="77e7e-102">ICorDebugClass::GetStaticFieldValue Method</span></span>
<span data-ttu-id="77e7e-103">지정 된 정적 필드의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="77e7e-103">Gets the value of the specified static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77e7e-104">구문</span><span class="sxs-lookup"><span data-stu-id="77e7e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef         fieldDef,  
    [in]  ICorDebugFrame     *pFrame,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77e7e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="77e7e-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="77e7e-106">진행 검색할 필드 `Def` 를 참조 하는 필드 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="77e7e-106">[in] A field `Def` token that references the field to be retrieved.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="77e7e-107">진행 스레드, 컨텍스트 또는 응용 프로그램 도메인 정적을 명확 하 게 구분 하는 데 사용할 프레임을 나타내는 ICorDebugFrame 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="77e7e-107">[in] A pointer to an ICorDebugFrame object that represents the frame to be used to disambiguate among thread, context, or application domain statics.</span></span>  
  
 <span data-ttu-id="77e7e-108">정적 필드가 스레드, 컨텍스트 또는 응용 프로그램 도메인을 기준으로 하는 경우 프레임에 적절 한 값이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77e7e-108">If the static field is relative to a thread, a context, or an application domain, the frame will determine the proper value.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="77e7e-109">제한이 정적 필드의 값을 나타내는 ICorDebugValue 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="77e7e-109">[out] A pointer to the address of an ICorDebugValue object that represents the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77e7e-110">설명</span><span class="sxs-lookup"><span data-stu-id="77e7e-110">Remarks</span></span>  
 <span data-ttu-id="77e7e-111">매개 변수가 있는 형식의 경우 정적 필드의 값은 특정 인스턴스화를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="77e7e-111">For parameterized types, the value of a static field is relative to the particular instantiation.</span></span> <span data-ttu-id="77e7e-112">따라서 클래스 생성자가 형식의 <xref:System.Type>매개 변수를 사용 하는 경우 대신 [ICorDebugType:: GetStaticFieldValue](icordebugtype-getstaticfieldvalue-method.md) 를 `ICorDebugClass::GetStaticFieldValue`호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="77e7e-112">Therefore, if the class constructor takes parameters of type <xref:System.Type>, call [ICorDebugType::GetStaticFieldValue](icordebugtype-getstaticfieldvalue-method.md) instead of `ICorDebugClass::GetStaticFieldValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77e7e-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="77e7e-113">Requirements</span></span>  
 <span data-ttu-id="77e7e-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="77e7e-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77e7e-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="77e7e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="77e7e-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77e7e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77e7e-117">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77e7e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
