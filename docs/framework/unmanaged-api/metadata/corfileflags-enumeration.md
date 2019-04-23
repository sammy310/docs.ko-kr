---
title: CorFileFlags 열거형
ms.date: 03/30/2017
api_name:
- CorFileFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFileFlags
helpviewer_keywords:
- CorFileFlags enumeration [.NET Framework metadata]
ms.assetid: d16703fd-518f-412e-92cb-74433d11032e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 076d5de3e9d1925e3a030fee4a06a89862105897
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59159616"
---
# <a name="corfileflags-enumeration"></a><span data-ttu-id="2b02b-102">CorFileFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="2b02b-102">CorFileFlags Enumeration</span></span>
<span data-ttu-id="2b02b-103">에 대 한 호출에 정의 된 파일의 형식을 설명 하는 값을 포함 [imetadataassemblyemit:: Definefile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2b02b-103">Contains values that describe the type of file defined in a call to [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b02b-104">구문</span><span class="sxs-lookup"><span data-stu-id="2b02b-104">Syntax</span></span>  
  
```  
typedef enum CorFileFlags {  
  
    ffContainsMetaData      =   0x0000,  
    ffContainsNoMetaData    =   0x0001  
  
} CorFileFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="2b02b-105">멤버</span><span class="sxs-lookup"><span data-stu-id="2b02b-105">Members</span></span>  
  
|<span data-ttu-id="2b02b-106">멤버</span><span class="sxs-lookup"><span data-stu-id="2b02b-106">Member</span></span>|<span data-ttu-id="2b02b-107">설명</span><span class="sxs-lookup"><span data-stu-id="2b02b-107">Description</span></span>|  
|------------|-----------------|  
|`ffContainsMetaData`|<span data-ttu-id="2b02b-108">파일 리소스 파일 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2b02b-108">Indicates that the file is not a resource file.</span></span>|  
|`ffContainsNoMetaData`|<span data-ttu-id="2b02b-109">가능한 경우 리소스 파일을 파일에 메타 데이터가 없습니다 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2b02b-109">Indicates that the file, possibly a resource file, does not contain metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2b02b-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2b02b-110">Requirements</span></span>  
 <span data-ttu-id="2b02b-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2b02b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b02b-112">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="2b02b-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="2b02b-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b02b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b02b-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="2b02b-114">See also</span></span>

- [<span data-ttu-id="2b02b-115">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="2b02b-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
