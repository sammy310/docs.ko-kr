---
description: '자세히 알아보기: ICorDebugILCode2 인터페이스'
title: ICorDebugILCode2 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugILCode2
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: f9dc2afd-df8a-464d-bdbf-5af0a1d4bf85
topic_type:
- apiref
ms.openlocfilehash: 52e47b8cbf8f9926797e193944fd7e97b2e4dbcd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791415"
---
# <a name="icordebugilcode2-interface"></a><span data-ttu-id="93726-103">ICorDebugILCode2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="93726-103">ICorDebugILCode2 Interface</span></span>

<span data-ttu-id="93726-104">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="93726-104">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="93726-105">는 [ICorDebugILCode](icordebugilcode-interface.md) 인터페이스를 논리적으로 확장 하 여 함수의 지역 변수 시그니처에 대 한 토큰을 반환 하는 메서드를 제공 하 고 프로파일러 계측 된 il (중간 언어) 오프셋을 원래 메서드 il 오프셋에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="93726-105">Logically extends the [ICorDebugILCode](icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="93726-106">메서드</span><span class="sxs-lookup"><span data-stu-id="93726-106">Methods</span></span>  
  
|<span data-ttu-id="93726-107">메서드</span><span class="sxs-lookup"><span data-stu-id="93726-107">Method</span></span>|<span data-ttu-id="93726-108">설명</span><span class="sxs-lookup"><span data-stu-id="93726-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="93726-109">GetInstrumentedILMap 메서드</span><span class="sxs-lookup"><span data-stu-id="93726-109">GetInstrumentedILMap Method</span></span>](icordebugilcode2-getinstrumentedilmap-method.md)|<span data-ttu-id="93726-110">이 인스턴스에 대해 프로파일러가 계측한 IL 오프셋에서 원래 메서드 IL 오프셋으로의 맵을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="93726-110">Returns a map from profiler instrumented IL offsets to original method IL offsets for this instance.</span></span>|  
|[<span data-ttu-id="93726-111">GetLocalVarSigToken 메서드</span><span class="sxs-lookup"><span data-stu-id="93726-111">GetLocalVarSigToken Method</span></span>](icordebugilcode2-getlocalvarsigtoken-method.md)|<span data-ttu-id="93726-112">이 인스턴스로 표시되는 함수의 로컬 변수 서명에 대한 메타데이터 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="93726-112">Gets the metadata token for the local variable signature for the function that is represented by this instance.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="93726-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="93726-113">Requirements</span></span>  

 <span data-ttu-id="93726-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="93726-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93726-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="93726-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="93726-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="93726-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="93726-117">**.NET Framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93726-117">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93726-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="93726-118">See also</span></span>

- [<span data-ttu-id="93726-119">ICorDebugILCode 인터페이스</span><span class="sxs-lookup"><span data-stu-id="93726-119">ICorDebugILCode Interface</span></span>](icordebugilcode-interface.md)
- [<span data-ttu-id="93726-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="93726-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="93726-121">디버깅</span><span class="sxs-lookup"><span data-stu-id="93726-121">Debugging</span></span>](index.md)
