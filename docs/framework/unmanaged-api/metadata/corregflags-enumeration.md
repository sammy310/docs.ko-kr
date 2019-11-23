---
title: CorRegFlags 열거형
ms.date: 03/30/2017
api_name:
- CorRegFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRegFlags
helpviewer_keywords:
- CorRegFlags enumeration [.NET Framework metadata]
ms.assetid: 8d3080ee-39fe-4c57-8950-51323632d045
topic_type:
- apiref
ms.openlocfilehash: 79a9e4513a98a29edc11cc76c599f03c9c3a72b4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450117"
---
# <a name="corregflags-enumeration"></a><span data-ttu-id="8fd48-102">CorRegFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="8fd48-102">CorRegFlags Enumeration</span></span>
<span data-ttu-id="8fd48-103">Provides flag values used for registration when installing a module or composite image.</span><span class="sxs-lookup"><span data-stu-id="8fd48-103">Provides flag values used for registration when installing a module or composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fd48-104">구문</span><span class="sxs-lookup"><span data-stu-id="8fd48-104">Syntax</span></span>  
  
```cpp  
typedef enum   
{  
    regNoCopy  = 0x00000001,  
    regConfig  = 0x00000002,  
    regHasRefs = 0x00000004  
} CorRegFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="8fd48-105">멤버</span><span class="sxs-lookup"><span data-stu-id="8fd48-105">Members</span></span>  
  
|<span data-ttu-id="8fd48-106">멤버</span><span class="sxs-lookup"><span data-stu-id="8fd48-106">Member</span></span>|<span data-ttu-id="8fd48-107">설명</span><span class="sxs-lookup"><span data-stu-id="8fd48-107">Description</span></span>|  
|------------|-----------------|  
|`regNoCopy`|<span data-ttu-id="8fd48-108">Specifies that files should not be copied into the destination.</span><span class="sxs-lookup"><span data-stu-id="8fd48-108">Specifies that files should not be copied into the destination.</span></span>|  
|`regConfig`|<span data-ttu-id="8fd48-109">Specifies that the module or composite is a configuration.</span><span class="sxs-lookup"><span data-stu-id="8fd48-109">Specifies that the module or composite is a configuration.</span></span>|  
|`regHasRefs`|<span data-ttu-id="8fd48-110">Specifies that the module or composite has class references.</span><span class="sxs-lookup"><span data-stu-id="8fd48-110">Specifies that the module or composite has class references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8fd48-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8fd48-111">Requirements</span></span>  
 <span data-ttu-id="8fd48-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8fd48-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fd48-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8fd48-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8fd48-114">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8fd48-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8fd48-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8fd48-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fd48-116">참조</span><span class="sxs-lookup"><span data-stu-id="8fd48-116">See also</span></span>

- [<span data-ttu-id="8fd48-117">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="8fd48-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
