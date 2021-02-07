---
description: '자세히 알아보기: IMetaDataDispenser 인터페이스'
title: IMetaDataDispenser 인터페이스
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser
helpviewer_keywords:
- IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 989840b3-9822-4ce5-a6c5-b375d3340a7a
topic_type:
- apiref
ms.openlocfilehash: 5ba37fc05a4e1897b100967d32b268f91a0e4402
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721010"
---
# <a name="imetadatadispenser-interface"></a><span data-ttu-id="d7fca-103">IMetaDataDispenser 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d7fca-103">IMetaDataDispenser Interface</span></span>

<span data-ttu-id="d7fca-104">새 메타 데이터 범위를 만들거나 기존 메타 데이터 범위를 여는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fca-104">Provides methods to create a new metadata scope, or open an existing one.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d7fca-105">메서드</span><span class="sxs-lookup"><span data-stu-id="d7fca-105">Methods</span></span>  
  
|<span data-ttu-id="d7fca-106">메서드</span><span class="sxs-lookup"><span data-stu-id="d7fca-106">Method</span></span>|<span data-ttu-id="d7fca-107">설명</span><span class="sxs-lookup"><span data-stu-id="d7fca-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d7fca-108">DefineScope 메서드</span><span class="sxs-lookup"><span data-stu-id="d7fca-108">DefineScope Method</span></span>](imetadatadispenser-definescope-method.md)|<span data-ttu-id="d7fca-109">새 메타 데이터를 만들 수 있는 메모리에 새 영역을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d7fca-109">Creates a new area in memory where you can create new metadata.</span></span>|  
|[<span data-ttu-id="d7fca-110">OpenScope 메서드</span><span class="sxs-lookup"><span data-stu-id="d7fca-110">OpenScope Method</span></span>](imetadatadispenser-openscope-method.md)|<span data-ttu-id="d7fca-111">기존 디스크에 있는 기존 파일을 열고 해당 메타 데이터를 메모리에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fca-111">Opens an existing, on-disk file and maps its metadata into memory.</span></span>|  
|[<span data-ttu-id="d7fca-112">OpenScopeOnMemory 메서드</span><span class="sxs-lookup"><span data-stu-id="d7fca-112">OpenScopeOnMemory Method</span></span>](imetadatadispenser-openscopeonmemory-method.md)|<span data-ttu-id="d7fca-113">기존 메타 데이터를 포함 하는 메모리 영역을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d7fca-113">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="d7fca-114">즉,이 메서드는 기존 데이터가 메타 데이터로 처리 되는 지정 된 메모리 영역을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d7fca-114">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d7fca-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d7fca-115">Requirements</span></span>  

 <span data-ttu-id="d7fca-116">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d7fca-116">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7fca-117">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="d7fca-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d7fca-118">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7fca-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d7fca-119">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7fca-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7fca-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d7fca-120">See also</span></span>

- [<span data-ttu-id="d7fca-121">IMetaDataDispenserEx 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d7fca-121">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="d7fca-122">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d7fca-122">Metadata Interfaces</span></span>](metadata-interfaces.md)
