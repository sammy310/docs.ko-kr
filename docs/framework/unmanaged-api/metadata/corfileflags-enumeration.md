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
ms.openlocfilehash: c315e2ae2753b59b4e277764d27c3fb3388b515c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445422"
---
# <a name="corfileflags-enumeration"></a><span data-ttu-id="58c26-102">CorFileFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="58c26-102">CorFileFlags Enumeration</span></span>
<span data-ttu-id="58c26-103">[IMetaDataAssemblyEmit::D efineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)호출에 정의 된 파일 형식을 설명 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="58c26-103">Contains values that describe the type of file defined in a call to [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58c26-104">구문</span><span class="sxs-lookup"><span data-stu-id="58c26-104">Syntax</span></span>  
  
```cpp  
typedef enum CorFileFlags {  
  
    ffContainsMetaData      =   0x0000,  
    ffContainsNoMetaData    =   0x0001  
  
} CorFileFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="58c26-105">멤버</span><span class="sxs-lookup"><span data-stu-id="58c26-105">Members</span></span>  
  
|<span data-ttu-id="58c26-106">멤버</span><span class="sxs-lookup"><span data-stu-id="58c26-106">Member</span></span>|<span data-ttu-id="58c26-107">설명</span><span class="sxs-lookup"><span data-stu-id="58c26-107">Description</span></span>|  
|------------|-----------------|  
|`ffContainsMetaData`|<span data-ttu-id="58c26-108">파일이 리소스 파일이 아님을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="58c26-108">Indicates that the file is not a resource file.</span></span>|  
|`ffContainsNoMetaData`|<span data-ttu-id="58c26-109">리소스 파일 일 수 있는 파일에 메타 데이터가 포함 되어 있지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="58c26-109">Indicates that the file, possibly a resource file, does not contain metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="58c26-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="58c26-110">Requirements</span></span>  
 <span data-ttu-id="58c26-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="58c26-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58c26-112">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="58c26-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="58c26-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58c26-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58c26-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="58c26-114">See also</span></span>

- [<span data-ttu-id="58c26-115">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="58c26-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
