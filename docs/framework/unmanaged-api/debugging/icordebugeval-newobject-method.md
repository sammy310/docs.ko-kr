---
title: ICorDebugEval::NewObject 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewObject
helpviewer_keywords:
- NewObject method [.NET Framework debugging]
- ICorDebugEval::NewObject method [.NET Framework debugging]
ms.assetid: ce3025e8-defa-4c5e-8298-f49d71fa5736
topic_type:
- apiref
ms.openlocfilehash: 68a7e911c2bd1798ea8f34f6a6e24299fe68775d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137617"
---
# <a name="icordebugevalnewobject-method"></a><span data-ttu-id="b9982-102">ICorDebugEval::NewObject 메서드</span><span class="sxs-lookup"><span data-stu-id="b9982-102">ICorDebugEval::NewObject Method</span></span>
<span data-ttu-id="b9982-103">새 개체 인스턴스를 할당 하 고 지정 된 생성자 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9982-103">Allocates a new object instance and calls the specified constructor method.</span></span>  
  
 <span data-ttu-id="b9982-104">이 메서드는 .NET Framework 버전 2.0에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b9982-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="b9982-105">대신 [ICorDebugEval2:: NewParameterizedObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) 를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9982-105">Use [ICorDebugEval2::NewParameterizedObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9982-106">구문</span><span class="sxs-lookup"><span data-stu-id="b9982-106">Syntax</span></span>  
  
```cpp  
HRESULT NewObject (  
    [in] ICorDebugFunction  *pConstructor,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9982-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b9982-107">Parameters</span></span>  
 `pConstructor`  
 <span data-ttu-id="b9982-108">진행 호출할 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="b9982-108">[in] The constructor to be called.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="b9982-109">[in] `ppArgs` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="b9982-109">[in] The size of the `ppArgs` array.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="b9982-110">진행 각각 생성자에 전달 되는 인수를 나타내는 ICorDebugValue 개체의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="b9982-110">[in] An array of ICorDebugValue objects, each of which represents an argument to be passed to the constructor.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9982-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b9982-111">Requirements</span></span>  
 <span data-ttu-id="b9982-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b9982-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9982-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b9982-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b9982-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9982-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9982-115">**.NET Framework 버전:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="b9982-115">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9982-116">참조</span><span class="sxs-lookup"><span data-stu-id="b9982-116">See also</span></span>

- [<span data-ttu-id="b9982-117">NewParameterizedObject 메서드</span><span class="sxs-lookup"><span data-stu-id="b9982-117">NewParameterizedObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)
