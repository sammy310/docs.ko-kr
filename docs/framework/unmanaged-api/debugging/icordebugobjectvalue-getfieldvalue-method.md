---
title: ICorDebugObjectValue::GetFieldValue 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.GetFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::GetFieldValue
helpviewer_keywords:
- ICorDebugObjectValue::GetFieldValue method [.NET Framework debugging]
- GetFieldValue method [.NET Framework debugging]
ms.assetid: c96770b0-3e09-47bb-bd29-20353b043459
topic_type:
- apiref
ms.openlocfilehash: 660bc13e8109994f59444c0adebbc97f54de0b43
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207584"
---
# <a name="icordebugobjectvaluegetfieldvalue-method"></a><span data-ttu-id="430c1-102">ICorDebugObjectValue::GetFieldValue 메서드</span><span class="sxs-lookup"><span data-stu-id="430c1-102">ICorDebugObjectValue::GetFieldValue Method</span></span>
<span data-ttu-id="430c1-103">이 개체 값에 대해 지정 된 클래스의 지정 된 필드 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="430c1-103">Gets the value of the specified field of the specified class for this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="430c1-104">구문</span><span class="sxs-lookup"><span data-stu-id="430c1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFieldValue (  
    [in]  ICorDebugClass     *pClass,  
    [in]  mdFieldDef         fieldDef,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="430c1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="430c1-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="430c1-106">진행 필드 값을 가져올 클래스를 나타내는 "ICorDebugClass" 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="430c1-106">[in] A pointer to an "ICorDebugClass" object that represents the class for which to get the field value.</span></span>  
  
 `fieldDef`  
 <span data-ttu-id="430c1-107">진행 `mdFieldDef`필드를 설명 하는 메타 데이터를 참조 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="430c1-107">[in] An `mdFieldDef` token that references the metadata describing the field.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="430c1-108">제한이 지정 된 필드의 값을 나타내는 "ICorDebugValue" 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="430c1-108">[out] A pointer to an "ICorDebugValue" object that represents the value of the specified field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="430c1-109">설명</span><span class="sxs-lookup"><span data-stu-id="430c1-109">Remarks</span></span>  
 <span data-ttu-id="430c1-110">매개 변수에 지정 된 클래스는 `pClass` 개체 값의 클래스 계층 구조에 있어야 하 고 필드는 해당 클래스의 필드 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="430c1-110">The class, specified in the `pClass` parameter, must be in the hierarchy of the object value's class, and the field must be a field of that class.</span></span>  
  
 <span data-ttu-id="430c1-111">`GetFieldValue`메서드는 제네릭 개체 및 제네릭 클래스에 대해 여전히 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="430c1-111">The `GetFieldValue` method will still succeed for generic objects and generic classes.</span></span> <span data-ttu-id="430c1-112">예를 들어 MyDictionary \< v> \< 가 사전 문자열, V>에서 상속 되 고 개체 값이 mydictionary> int32 형식이 면, \< V>는 사전 `ICorDebugClass` \< 문자열 int32>의 필드를 성공적으로 가져옵니다 \< .</span><span class="sxs-lookup"><span data-stu-id="430c1-112">For example, if MyDictionary\<V> inherits from Dictionary\<string,V>, and the object value is of type MyDictionary\<int32>, passing the `ICorDebugClass` object for Dictionary\<K,V> will successfully get a field of Dictionary\<string,int32>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="430c1-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="430c1-113">Requirements</span></span>  
 <span data-ttu-id="430c1-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="430c1-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="430c1-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="430c1-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="430c1-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="430c1-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="430c1-117">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="430c1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="430c1-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="430c1-118">See also</span></span>
