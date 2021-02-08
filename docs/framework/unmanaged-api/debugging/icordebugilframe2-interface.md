---
description: '자세히 알아보기: ICorDebugILFrame2 인터페이스'
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
ms.openlocfilehash: 8379fda39a210e1df902dab3ac85132f04aee5fc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791311"
---
# <a name="icordebugilframe2-interface"></a><span data-ttu-id="a9014-103">ICorDebugILFrame2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a9014-103">ICorDebugILFrame2 Interface</span></span>

<span data-ttu-id="a9014-104">ICorDebugILFrame 인터페이스의 논리적 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="a9014-104">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a9014-105">메서드</span><span class="sxs-lookup"><span data-stu-id="a9014-105">Methods</span></span>  
  
|<span data-ttu-id="a9014-106">메서드</span><span class="sxs-lookup"><span data-stu-id="a9014-106">Method</span></span>|<span data-ttu-id="a9014-107">설명</span><span class="sxs-lookup"><span data-stu-id="a9014-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a9014-108">EnumerateTypeParameters 메서드</span><span class="sxs-lookup"><span data-stu-id="a9014-108">EnumerateTypeParameters Method</span></span>](icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="a9014-109">이 프레임의 매개 변수를 포함 하는 ICorDebugTypeEnum 개체를 가져옵니다 <xref:System.Type> .</span><span class="sxs-lookup"><span data-stu-id="a9014-109">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="a9014-110">RemapFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="a9014-110">RemapFunction Method</span></span>](icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="a9014-111">새 MSIL 오프셋을 지정 하 여 편집 된 함수를 다시 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="a9014-111">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9014-112">설명</span><span class="sxs-lookup"><span data-stu-id="a9014-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a9014-113">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a9014-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9014-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a9014-114">Requirements</span></span>  

 <span data-ttu-id="a9014-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a9014-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9014-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a9014-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a9014-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9014-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9014-118">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9014-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9014-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a9014-119">See also</span></span>

- [<span data-ttu-id="a9014-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a9014-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
