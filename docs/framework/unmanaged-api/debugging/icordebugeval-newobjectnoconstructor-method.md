---
title: ICorDebugEval::NewObjectNoConstructor 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewObjectNoConstructor
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewObjectNoConstructor
helpviewer_keywords:
- NewObjectNoConstructor method [.NET Framework debugging]
- ICorDebugEval::NewObjectNoConstructor method [.NET Framework debugging]
ms.assetid: 80d509ca-b5e3-4c46-9c14-800db73d9bf7
topic_type:
- apiref
ms.openlocfilehash: 255d88dcdd880c73a7535cddcad410dcfdcf1d70
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132656"
---
# <a name="icordebugevalnewobjectnoconstructor-method"></a><span data-ttu-id="8fd00-102">ICorDebugEval::NewObjectNoConstructor 메서드</span><span class="sxs-lookup"><span data-stu-id="8fd00-102">ICorDebugEval::NewObjectNoConstructor Method</span></span>
<span data-ttu-id="8fd00-103">생성자 메서드 호출을 시도 하지 않고 지정 된 형식의 새 개체 인스턴스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd00-103">Allocates a new object instance of the specified type, without attempting to call a constructor method.</span></span>  
  
 <span data-ttu-id="8fd00-104">이 메서드는 .NET Framework 버전 2.0에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8fd00-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="8fd00-105">대신 [ICorDebugEval2:: NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) 를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd00-105">Use [ICorDebugEval2::NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fd00-106">구문</span><span class="sxs-lookup"><span data-stu-id="8fd00-106">Syntax</span></span>  
  
```cpp  
HRESULT NewObjectNoConstructor (  
    [in] ICorDebugClass     *pClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8fd00-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8fd00-107">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="8fd00-108">진행 인스턴스화할 개체의 형식을 나타내는 ICorDebugClass 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8fd00-108">[in] Pointer to an ICorDebugClass object that represents the type of object to be instantiated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8fd00-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8fd00-109">Requirements</span></span>  
 <span data-ttu-id="8fd00-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8fd00-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fd00-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8fd00-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8fd00-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8fd00-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8fd00-113">**.NET Framework 버전:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="8fd00-113">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fd00-114">참조</span><span class="sxs-lookup"><span data-stu-id="8fd00-114">See also</span></span>

- [<span data-ttu-id="8fd00-115">NewParameterizedObjectNoConstructor 메서드</span><span class="sxs-lookup"><span data-stu-id="8fd00-115">NewParameterizedObjectNoConstructor Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)
