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
ms.openlocfilehash: 38cc98f1bfd966d1f764e43b30003a2bae66297d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793466"
---
# <a name="icordebugevalnewobject-method"></a><span data-ttu-id="2b8cb-102">ICorDebugEval::NewObject 메서드</span><span class="sxs-lookup"><span data-stu-id="2b8cb-102">ICorDebugEval::NewObject Method</span></span>
<span data-ttu-id="2b8cb-103">새 개체 인스턴스를 할당 하 고 지정 된 생성자 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b8cb-103">Allocates a new object instance and calls the specified constructor method.</span></span>  
  
 <span data-ttu-id="2b8cb-104">이 메서드는 .NET Framework 버전 2.0에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b8cb-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="2b8cb-105">대신 [ICorDebugEval2:: NewParameterizedObject](icordebugeval2-newparameterizedobject-method.md) 를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b8cb-105">Use [ICorDebugEval2::NewParameterizedObject](icordebugeval2-newparameterizedobject-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b8cb-106">구문</span><span class="sxs-lookup"><span data-stu-id="2b8cb-106">Syntax</span></span>  
  
```cpp  
HRESULT NewObject (  
    [in] ICorDebugFunction  *pConstructor,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b8cb-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2b8cb-107">Parameters</span></span>  
 `pConstructor`  
 <span data-ttu-id="2b8cb-108">진행 호출할 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="2b8cb-108">[in] The constructor to be called.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="2b8cb-109">[in] `ppArgs` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="2b8cb-109">[in] The size of the `ppArgs` array.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="2b8cb-110">진행 각각 생성자에 전달 되는 인수를 나타내는 ICorDebugValue 개체의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="2b8cb-110">[in] An array of ICorDebugValue objects, each of which represents an argument to be passed to the constructor.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b8cb-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2b8cb-111">Requirements</span></span>  
 <span data-ttu-id="2b8cb-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2b8cb-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b8cb-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2b8cb-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2b8cb-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b8cb-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b8cb-115">**.NET Framework 버전:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="2b8cb-115">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b8cb-116">참조</span><span class="sxs-lookup"><span data-stu-id="2b8cb-116">See also</span></span>

- [<span data-ttu-id="2b8cb-117">NewParameterizedObject 메서드</span><span class="sxs-lookup"><span data-stu-id="2b8cb-117">NewParameterizedObject Method</span></span>](icordebugeval2-newparameterizedobject-method.md)
