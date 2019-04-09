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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 820c99de1bdb108a24203a3438b1709ca54490b7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078124"
---
# <a name="corfieldoffset-structure"></a><span data-ttu-id="55f54-102">COR_FIELD_OFFSET 구조체</span><span class="sxs-lookup"><span data-stu-id="55f54-102">COR_FIELD_OFFSET Structure</span></span>
<span data-ttu-id="55f54-103">클래스 내에서 지정된 필드의 오프셋을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="55f54-103">Stores the offset, within a class, of the specified field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55f54-104">구문</span><span class="sxs-lookup"><span data-stu-id="55f54-104">Syntax</span></span>  
  
```  
typedef struct COR_FIELD_OFFSET {  
    mdFieldDef  ridOfField;  
    ULONG       ulOffset;  
} COR_FIELD_OFFSET;  
```  
  
## <a name="members"></a><span data-ttu-id="55f54-105">멤버</span><span class="sxs-lookup"><span data-stu-id="55f54-105">Members</span></span>  
  
|<span data-ttu-id="55f54-106">멤버</span><span class="sxs-lookup"><span data-stu-id="55f54-106">Member</span></span>|<span data-ttu-id="55f54-107">설명</span><span class="sxs-lookup"><span data-stu-id="55f54-107">Description</span></span>|  
|------------|-----------------|  
|`ridOfField`|<span data-ttu-id="55f54-108">`mdFieldDef` 필드를 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="55f54-108">An `mdFieldDef` metadata token that represents the field.</span></span>|  
|`ulOffset`|<span data-ttu-id="55f54-109">클래스 내의 필드 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="55f54-109">The field's offset within its class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55f54-110">설명</span><span class="sxs-lookup"><span data-stu-id="55f54-110">Remarks</span></span>  
 <span data-ttu-id="55f54-111">[Imetadataimport:: Getclasslayout](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getclasslayout-method.md) 하 고 [imetadataemit:: Setclasslayout](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setclasslayout-method.md) 형식의 매개 변수를 사용 하는 메서드 `COR_FIELD_OFFSET`합니다.</span><span class="sxs-lookup"><span data-stu-id="55f54-111">[IMetaDataImport::GetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getclasslayout-method.md) and [IMetaDataEmit::SetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setclasslayout-method.md) methods take a parameter of type `COR_FIELD_OFFSET`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55f54-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="55f54-112">Requirements</span></span>  
 <span data-ttu-id="55f54-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="55f54-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55f54-114">**헤더:** CorHdr.h, CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="55f54-114">**Header:** CorHdr.h, CorProf.idl</span></span>  
  
 **<span data-ttu-id="55f54-115">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="55f54-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="55f54-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="55f54-116">See also</span></span>

- [<span data-ttu-id="55f54-117">메타데이터 구조체</span><span class="sxs-lookup"><span data-stu-id="55f54-117">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="55f54-118">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="55f54-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="55f54-119">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="55f54-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
