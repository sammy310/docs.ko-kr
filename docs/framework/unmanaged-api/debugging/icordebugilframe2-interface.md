---
title: ICorDebugILFrame2 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2
helpviewer_keywords:
- ICorDebugILFrame2 interface [.NET Framework debugging]
ms.assetid: f94b9d53-d8f8-4424-a95e-53a1bfd26e4a
topic_type:
- apiref
ms.openlocfilehash: c5fa0a67309e23c02393b70d849af3884dfd0adf
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788537"
---
# <a name="icordebugilframe2-interface"></a><span data-ttu-id="66ca2-102">ICorDebugILFrame2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="66ca2-102">ICorDebugILFrame2 Interface</span></span>

<span data-ttu-id="66ca2-103">ICorDebugILFrame 인터페이스의 논리적 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="66ca2-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="66ca2-104">메서드</span><span class="sxs-lookup"><span data-stu-id="66ca2-104">Methods</span></span>  
  
|<span data-ttu-id="66ca2-105">메서드</span><span class="sxs-lookup"><span data-stu-id="66ca2-105">Method</span></span>|<span data-ttu-id="66ca2-106">설명</span><span class="sxs-lookup"><span data-stu-id="66ca2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="66ca2-107">EnumerateTypeParameters 메서드</span><span class="sxs-lookup"><span data-stu-id="66ca2-107">EnumerateTypeParameters Method</span></span>](icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="66ca2-108">이 프레임의 <xref:System.Type> 매개 변수를 포함 하는 ICorDebugTypeEnum 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="66ca2-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="66ca2-109">RemapFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="66ca2-109">RemapFunction Method</span></span>](icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="66ca2-110">새 MSIL 오프셋을 지정 하 여 편집 된 함수를 다시 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="66ca2-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="66ca2-111">주의</span><span class="sxs-lookup"><span data-stu-id="66ca2-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="66ca2-112">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66ca2-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66ca2-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="66ca2-113">Requirements</span></span>  
 <span data-ttu-id="66ca2-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66ca2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66ca2-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="66ca2-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="66ca2-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66ca2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66ca2-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66ca2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66ca2-118">참조</span><span class="sxs-lookup"><span data-stu-id="66ca2-118">See also</span></span>

- [<span data-ttu-id="66ca2-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="66ca2-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
