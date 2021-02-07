---
description: '다음에 대 한 자세한 정보: COR_FIELD_OFFSET 구조체'
title: COR_FIELD_OFFSET 구조체
ms.date: 03/30/2017
api_name:
- COR_FIELD_OFFSET
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_FIELD_OFFSET
helpviewer_keywords:
- COR_FIELD_OFFSET structure [.NET Framework metadata]
ms.assetid: cced5298-277f-4a5a-8ecf-a0050c1096ea
topic_type:
- apiref
ms.openlocfilehash: 7976e79a5484fa467d7ac887a4e1a7fa324abf69
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678629"
---
# <a name="cor_field_offset-structure"></a><span data-ttu-id="8879d-103">COR_FIELD_OFFSET 구조체</span><span class="sxs-lookup"><span data-stu-id="8879d-103">COR_FIELD_OFFSET Structure</span></span>

<span data-ttu-id="8879d-104">클래스 내에서 지정된 필드의 오프셋을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="8879d-104">Stores the offset, within a class, of the specified field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8879d-105">구문</span><span class="sxs-lookup"><span data-stu-id="8879d-105">Syntax</span></span>  
  
```cpp  
typedef struct COR_FIELD_OFFSET {  
    mdFieldDef  ridOfField;  
    ULONG       ulOffset;  
} COR_FIELD_OFFSET;  
```  
  
## <a name="members"></a><span data-ttu-id="8879d-106">구성원</span><span class="sxs-lookup"><span data-stu-id="8879d-106">Members</span></span>  
  
|<span data-ttu-id="8879d-107">멤버</span><span class="sxs-lookup"><span data-stu-id="8879d-107">Member</span></span>|<span data-ttu-id="8879d-108">설명</span><span class="sxs-lookup"><span data-stu-id="8879d-108">Description</span></span>|  
|------------|-----------------|  
|`ridOfField`|<span data-ttu-id="8879d-109">`mdFieldDef`필드를 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="8879d-109">An `mdFieldDef` metadata token that represents the field.</span></span>|  
|`ulOffset`|<span data-ttu-id="8879d-110">클래스 내의 필드 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="8879d-110">The field's offset within its class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8879d-111">설명</span><span class="sxs-lookup"><span data-stu-id="8879d-111">Remarks</span></span>  

 <span data-ttu-id="8879d-112">[IMetaDataImport:: GetClassLayout](imetadataimport-getclasslayout-method.md) 및 [IMetaDataEmit:: SetClassLayout](imetadataemit-setclasslayout-method.md) 메서드는 형식의 매개 변수를 사용 `COR_FIELD_OFFSET` 합니다.</span><span class="sxs-lookup"><span data-stu-id="8879d-112">[IMetaDataImport::GetClassLayout](imetadataimport-getclasslayout-method.md) and [IMetaDataEmit::SetClassLayout](imetadataemit-setclasslayout-method.md) methods take a parameter of type `COR_FIELD_OFFSET`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8879d-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8879d-113">Requirements</span></span>  

 <span data-ttu-id="8879d-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8879d-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8879d-115">**헤더:** CorHdr .h, Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="8879d-115">**Header:** CorHdr.h, CorProf.idl</span></span>  
  
 <span data-ttu-id="8879d-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8879d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8879d-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8879d-117">See also</span></span>

- [<span data-ttu-id="8879d-118">메타데이터 구조체</span><span class="sxs-lookup"><span data-stu-id="8879d-118">Metadata Structures</span></span>](metadata-structures.md)
- [<span data-ttu-id="8879d-119">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8879d-119">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="8879d-120">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8879d-120">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
