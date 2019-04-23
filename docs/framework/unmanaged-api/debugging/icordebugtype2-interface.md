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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 878941f7af71fa5e3de8e38c4a68a66cb964983d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59223162"
---
# <a name="icordebugtype2-interface"></a><span data-ttu-id="851ac-102">ICorDebugType2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="851ac-102">ICorDebugType2 Interface</span></span>
<span data-ttu-id="851ac-103">ICorDebugType 인터페이스는 기본 형식 또는 복합 (사용자 정의 됨) 형식의 형식 식별자를 검색 하는 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="851ac-103">Extends the ICorDebugType interface to retrieve the type identifier  of a base type or complex (user-defined) type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="851ac-104">메서드</span><span class="sxs-lookup"><span data-stu-id="851ac-104">Methods</span></span>  
  
|<span data-ttu-id="851ac-105">메서드</span><span class="sxs-lookup"><span data-stu-id="851ac-105">Method</span></span>||  
|------------|-|  
|[<span data-ttu-id="851ac-106">GetTypeID 메서드</span><span class="sxs-lookup"><span data-stu-id="851ac-106">GetTypeID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-gettypeid-method.md)|<span data-ttu-id="851ac-107">가져옵니다를 [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) 이 형식에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="851ac-107">Gets a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) for this type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="851ac-108">설명</span><span class="sxs-lookup"><span data-stu-id="851ac-108">Remarks</span></span>  
 <span data-ttu-id="851ac-109">이 인터페이스는 ICorDebugType 인터페이스를 논리적으로 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="851ac-109">This interface is a logical extension of the ICorDebugType interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="851ac-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="851ac-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="example"></a><span data-ttu-id="851ac-111">예제</span><span class="sxs-lookup"><span data-stu-id="851ac-111">Example</span></span>  
 <span data-ttu-id="851ac-112">다음 코드 조각에서는 사용 합니다 [ICorDebugType2::GetTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-gettypeid-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="851ac-112">The following code fragment illustrates the use of the [ICorDebugType2::GetTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-gettypeid-method.md) method.</span></span>  
  
```  
// (error checking omitted for brevity)  
// given an ICorDebugType *pType  
  
ICorDebugType2 *pType2 = NULL;  
pType->QueryInterface(IID_ICorDebugType2, &pType);  
  
COR_TYPEID id;  
pType2->GetTypeID(&id);  
  
// now we can use existing APIs to get information about this COR_TYPEID  
```  
  
## <a name="requirements"></a><span data-ttu-id="851ac-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="851ac-113">Requirements</span></span>  
 <span data-ttu-id="851ac-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="851ac-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="851ac-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="851ac-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="851ac-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="851ac-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="851ac-117">**.NET Framework 버전:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="851ac-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="851ac-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="851ac-118">See also</span></span>

- [<span data-ttu-id="851ac-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="851ac-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
