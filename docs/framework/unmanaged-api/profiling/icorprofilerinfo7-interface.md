---
description: '자세히 알아보기: ICorProfilerInfo7 인터페이스'
title: ICorProfilerInfo7 인터페이스
ms.date: 03/30/2017
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
ms.openlocfilehash: 7a33472d5562ad57d38291c64f8da7021ae2fe91
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737079"
---
# <a name="icorprofilerinfo7-interface"></a><span data-ttu-id="0cc43-103">ICorProfilerInfo7 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0cc43-103">ICorProfilerInfo7 Interface</span></span>

<span data-ttu-id="0cc43-104">[.NET Framework 4.6.1 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="0cc43-104">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="0cc43-105">새로 정의 된 메타 데이터를 모듈에 적용 하 고 메모리 내 기호 스트림에 대 한 액세스를 제공 하는 메서드를 제공 하는 [ICorProfilerInfo6](icorprofilerinfo6-interface.md) 의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="0cc43-105">A subclass of [ICorProfilerInfo6](icorprofilerinfo6-interface.md) that provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0cc43-106">메서드</span><span class="sxs-lookup"><span data-stu-id="0cc43-106">Methods</span></span>  
  
|<span data-ttu-id="0cc43-107">메서드</span><span class="sxs-lookup"><span data-stu-id="0cc43-107">Method</span></span>|<span data-ttu-id="0cc43-108">설명</span><span class="sxs-lookup"><span data-stu-id="0cc43-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0cc43-109">ApplyMetaData 메서드</span><span class="sxs-lookup"><span data-stu-id="0cc43-109">ApplyMetaData Method</span></span>](icorprofilerinfo7-applymetadata-method.md)|<span data-ttu-id="0cc43-110">메서드에 의해 새로 정의 된 메타 데이터를 `IMetadataEmit::Define*` 지정 된 모듈에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cc43-110">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>|  
|[<span data-ttu-id="0cc43-111">GetInMemorySymbolsLength 메서드</span><span class="sxs-lookup"><span data-stu-id="0cc43-111">GetInMemorySymbolsLength Method</span></span>](icorprofilerinfo7-getinmemorysymbolslength-method.md)|<span data-ttu-id="0cc43-112">메모리 내 기호 스트림의 길이를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cc43-112">Returns the length of an in-memory symbol stream.</span></span>|  
|[<span data-ttu-id="0cc43-113">ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="0cc43-113">ReadInMemorySymbols</span></span>](icorprofilerinfo7-readinmemorysymbols.md)|<span data-ttu-id="0cc43-114">메모리 내 기호 스트림에서 바이트를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="0cc43-114">Reads bytes from an in-memory symbol stream.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0cc43-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0cc43-115">Requirements</span></span>  

 <span data-ttu-id="0cc43-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0cc43-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cc43-117">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0cc43-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0cc43-118">**.NET Framework 버전:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0cc43-118">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cc43-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0cc43-119">See also</span></span>

- [<span data-ttu-id="0cc43-120">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0cc43-120">Profiling Interfaces</span></span>](profiling-interfaces.md)
