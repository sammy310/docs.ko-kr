---
description: '자세히 알아보기: ICorDebugNativeFrame2 인터페이스'
title: ICorDebugNativeFrame2 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2
helpviewer_keywords:
- ICorDebugNativeFrame2 interface [.NET Framework debugging]
ms.assetid: 52a80838-af36-4399-bc97-d8a4c6d76df2
topic_type:
- apiref
ms.openlocfilehash: 9ed0e20bb29bef3b210258956ebecb1ee7a96df8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722349"
---
# <a name="icordebugnativeframe2-interface"></a><span data-ttu-id="6ac04-103">ICorDebugNativeFrame2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6ac04-103">ICorDebugNativeFrame2 Interface</span></span>

<span data-ttu-id="6ac04-104">자식 및 부모 프레임 관계를 테스트하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6ac04-104">Provides methods that test for child and parent frame relationships.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6ac04-105">메서드</span><span class="sxs-lookup"><span data-stu-id="6ac04-105">Methods</span></span>  
  
|<span data-ttu-id="6ac04-106">메서드</span><span class="sxs-lookup"><span data-stu-id="6ac04-106">Method</span></span>|<span data-ttu-id="6ac04-107">설명</span><span class="sxs-lookup"><span data-stu-id="6ac04-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6ac04-108">IsChild 메서드</span><span class="sxs-lookup"><span data-stu-id="6ac04-108">IsChild Method</span></span>](icordebugnativeframe2-ischild-method.md)|<span data-ttu-id="6ac04-109">현재 프레임이 자식 프레임 인지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ac04-109">Determines whether the current frame is a child frame.</span></span>|  
|[<span data-ttu-id="6ac04-110">IsMatchingParentFrame 메서드</span><span class="sxs-lookup"><span data-stu-id="6ac04-110">IsMatchingParentFrame Method</span></span>](icordebugnativeframe2-ismatchingparentframe-method.md)|<span data-ttu-id="6ac04-111">지정 된 프레임이 현재 프레임의 부모 인지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ac04-111">Determines whether the specified frame is the parent of the current frame.</span></span>|  
|[<span data-ttu-id="6ac04-112">GetStackParameterSize 메서드</span><span class="sxs-lookup"><span data-stu-id="6ac04-112">GetStackParameterSize Method</span></span>](icordebugnativeframe2-getstackparametersize-method.md)|<span data-ttu-id="6ac04-113">X86 운영 체제의 스택에 있는 매개 변수의 누적 크기를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ac04-113">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ac04-114">설명</span><span class="sxs-lookup"><span data-stu-id="6ac04-114">Remarks</span></span>  

 <span data-ttu-id="6ac04-115">이 인터페이스는 "ICorDebugNativeFrame" 인터페이스를 논리적으로 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ac04-115">This interface logically extends the "ICorDebugNativeFrame" interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6ac04-116">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ac04-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ac04-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6ac04-117">Requirements</span></span>  

 <span data-ttu-id="6ac04-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ac04-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ac04-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6ac04-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6ac04-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ac04-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ac04-121">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ac04-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ac04-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6ac04-122">See also</span></span>

- [<span data-ttu-id="6ac04-123">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6ac04-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="6ac04-124">디버깅</span><span class="sxs-lookup"><span data-stu-id="6ac04-124">Debugging</span></span>](index.md)
