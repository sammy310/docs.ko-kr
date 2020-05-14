---
title: ICorDebugType2 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugType2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType2
helpviewer_keywords:
- ICorDebugType2 interface
ms.assetid: 376fb03f-f1ef-4107-baa4-4d9d55884862
topic_type:
- apiref
ms.openlocfilehash: 0e480db953131d7771e493a8f367154a7d17dada
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396635"
---
# <a name="icordebugtype2-interface"></a><span data-ttu-id="df03c-102">ICorDebugType2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="df03c-102">ICorDebugType2 Interface</span></span>
<span data-ttu-id="df03c-103">ICorDebugType 인터페이스를 확장 하 여 기본 형식 또는 복합 (사용자 정의) 형식의 형식 식별자를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="df03c-103">Extends the ICorDebugType interface to retrieve the type identifier  of a base type or complex (user-defined) type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="df03c-104">메서드</span><span class="sxs-lookup"><span data-stu-id="df03c-104">Methods</span></span>  
  
|<span data-ttu-id="df03c-105">메서드</span><span class="sxs-lookup"><span data-stu-id="df03c-105">Method</span></span>||  
|------------|-|  
|[<span data-ttu-id="df03c-106">GetTypeID 메서드</span><span class="sxs-lookup"><span data-stu-id="df03c-106">GetTypeID Method</span></span>](icordebugtype2-gettypeid-method.md)|<span data-ttu-id="df03c-107">이 형식에 대 한 [COR_TYPEID](cor-typeid-structure.md) 를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="df03c-107">Gets a [COR_TYPEID](cor-typeid-structure.md) for this type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="df03c-108">설명</span><span class="sxs-lookup"><span data-stu-id="df03c-108">Remarks</span></span>  
 <span data-ttu-id="df03c-109">이 인터페이스는 ICorDebugType 인터페이스의 논리적 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="df03c-109">This interface is a logical extension of the ICorDebugType interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="df03c-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="df03c-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="example"></a><span data-ttu-id="df03c-111">예제</span><span class="sxs-lookup"><span data-stu-id="df03c-111">Example</span></span>  
 <span data-ttu-id="df03c-112">다음 코드 조각에서는 [ICorDebugType2:: GetTypeID](icordebugtype2-gettypeid-method.md) 메서드를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="df03c-112">The following code fragment illustrates the use of the [ICorDebugType2::GetTypeID](icordebugtype2-gettypeid-method.md) method.</span></span>  
  
```cpp  
// (error checking omitted for brevity)  
// given an ICorDebugType *pType  
  
ICorDebugType2 *pType2 = NULL;  
pType->QueryInterface(IID_ICorDebugType2, &pType);  
  
COR_TYPEID id;  
pType2->GetTypeID(&id);  
  
// now we can use existing APIs to get information about this COR_TYPEID  
```  
  
## <a name="requirements"></a><span data-ttu-id="df03c-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="df03c-113">Requirements</span></span>  
 <span data-ttu-id="df03c-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="df03c-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df03c-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="df03c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="df03c-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df03c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df03c-117">**.NET Framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df03c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df03c-118">참조</span><span class="sxs-lookup"><span data-stu-id="df03c-118">See also</span></span>

- [<span data-ttu-id="df03c-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="df03c-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
