---
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
ms.openlocfilehash: 1a8ab5aa5909af60089d5e4cc8092e15bc75e8cc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724184"
---
# <a name="cor_field_offset-structure"></a><span data-ttu-id="ef245-102">COR_FIELD_OFFSET 구조체</span><span class="sxs-lookup"><span data-stu-id="ef245-102">COR_FIELD_OFFSET Structure</span></span>

<span data-ttu-id="ef245-103">클래스 내에서 지정된 필드의 오프셋을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="ef245-103">Stores the offset, within a class, of the specified field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef245-104">구문</span><span class="sxs-lookup"><span data-stu-id="ef245-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_FIELD_OFFSET {  
    mdFieldDef  ridOfField;  
    ULONG       ulOffset;  
} COR_FIELD_OFFSET;  
```  
  
## <a name="members"></a><span data-ttu-id="ef245-105">멤버</span><span class="sxs-lookup"><span data-stu-id="ef245-105">Members</span></span>  
  
|<span data-ttu-id="ef245-106">멤버</span><span class="sxs-lookup"><span data-stu-id="ef245-106">Member</span></span>|<span data-ttu-id="ef245-107">설명</span><span class="sxs-lookup"><span data-stu-id="ef245-107">Description</span></span>|  
|------------|-----------------|  
|`ridOfField`|<span data-ttu-id="ef245-108">`mdFieldDef`필드를 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ef245-108">An `mdFieldDef` metadata token that represents the field.</span></span>|  
|`ulOffset`|<span data-ttu-id="ef245-109">클래스 내의 필드 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="ef245-109">The field's offset within its class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef245-110">설명</span><span class="sxs-lookup"><span data-stu-id="ef245-110">Remarks</span></span>  

 <span data-ttu-id="ef245-111">[IMetaDataImport:: GetClassLayout](imetadataimport-getclasslayout-method.md) 및 [IMetaDataEmit:: SetClassLayout](imetadataemit-setclasslayout-method.md) 메서드는 형식의 매개 변수를 사용 `COR_FIELD_OFFSET` 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef245-111">[IMetaDataImport::GetClassLayout](imetadataimport-getclasslayout-method.md) and [IMetaDataEmit::SetClassLayout](imetadataemit-setclasslayout-method.md) methods take a parameter of type `COR_FIELD_OFFSET`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef245-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ef245-112">Requirements</span></span>  

 <span data-ttu-id="ef245-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ef245-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef245-114">**헤더:** CorHdr .h, Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="ef245-114">**Header:** CorHdr.h, CorProf.idl</span></span>  
  
 <span data-ttu-id="ef245-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef245-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef245-116">참조</span><span class="sxs-lookup"><span data-stu-id="ef245-116">See also</span></span>

- [<span data-ttu-id="ef245-117">메타데이터 구조체</span><span class="sxs-lookup"><span data-stu-id="ef245-117">Metadata Structures</span></span>](metadata-structures.md)
- [<span data-ttu-id="ef245-118">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ef245-118">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="ef245-119">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ef245-119">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
