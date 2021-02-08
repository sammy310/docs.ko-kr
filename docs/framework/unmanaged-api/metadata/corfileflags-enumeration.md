---
description: '다음에 대 한 자세한 정보: CorFileFlags 열거형'
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
ms.openlocfilehash: 8ffad9bad9c656a10c2c556f5e06f9d510ccb45a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784485"
---
# <a name="corfileflags-enumeration"></a><span data-ttu-id="6d6e7-103">CorFileFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="6d6e7-103">CorFileFlags Enumeration</span></span>

<span data-ttu-id="6d6e7-104">[IMetaDataAssemblyEmit::D efineFile](imetadataassemblyemit-definefile-method.md)호출에 정의 된 파일 형식을 설명 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d6e7-104">Contains values that describe the type of file defined in a call to [IMetaDataAssemblyEmit::DefineFile](imetadataassemblyemit-definefile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d6e7-105">구문</span><span class="sxs-lookup"><span data-stu-id="6d6e7-105">Syntax</span></span>  
  
```cpp  
typedef enum CorFileFlags {  
  
    ffContainsMetaData      =   0x0000,  
    ffContainsNoMetaData    =   0x0001  
  
} CorFileFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="6d6e7-106">구성원</span><span class="sxs-lookup"><span data-stu-id="6d6e7-106">Members</span></span>  
  
|<span data-ttu-id="6d6e7-107">멤버</span><span class="sxs-lookup"><span data-stu-id="6d6e7-107">Member</span></span>|<span data-ttu-id="6d6e7-108">설명</span><span class="sxs-lookup"><span data-stu-id="6d6e7-108">Description</span></span>|  
|------------|-----------------|  
|`ffContainsMetaData`|<span data-ttu-id="6d6e7-109">파일이 리소스 파일이 아님을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6d6e7-109">Indicates that the file is not a resource file.</span></span>|  
|`ffContainsNoMetaData`|<span data-ttu-id="6d6e7-110">리소스 파일 일 수 있는 파일에 메타 데이터가 포함 되어 있지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6d6e7-110">Indicates that the file, possibly a resource file, does not contain metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6d6e7-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6d6e7-111">Requirements</span></span>  

 <span data-ttu-id="6d6e7-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6d6e7-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d6e7-113">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="6d6e7-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="6d6e7-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d6e7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d6e7-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6d6e7-115">See also</span></span>

- [<span data-ttu-id="6d6e7-116">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="6d6e7-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
