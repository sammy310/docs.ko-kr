---
title: AssemblyRefFlags 열거형
ms.date: 03/30/2017
api_name:
- AssemblyRefFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyRefFlags
helpviewer_keywords:
- AssemblyRefFlags enumeration [.NET Framework metadata]
ms.assetid: decd4f46-f3b2-466f-9501-e74f2b86b846
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bc98b2421d23ffd6dfb716a8cc782b46a9d59ce0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59128898"
---
# <a name="assemblyrefflags-enumeration"></a><span data-ttu-id="aa06d-102">AssemblyRefFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="aa06d-102">AssemblyRefFlags Enumeration</span></span>
<span data-ttu-id="aa06d-103">어셈블리 참조의 기능을 설명 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa06d-103">Contains values that describe features of an assembly reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa06d-104">구문</span><span class="sxs-lookup"><span data-stu-id="aa06d-104">Syntax</span></span>  
  
```  
typedef enum {  
    arfFullOriginator = 0x0001  
} AssemblyRefFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="aa06d-105">멤버</span><span class="sxs-lookup"><span data-stu-id="aa06d-105">Members</span></span>  
  
|<span data-ttu-id="aa06d-106">멤버</span><span class="sxs-lookup"><span data-stu-id="aa06d-106">Member</span></span>|<span data-ttu-id="aa06d-107">설명</span><span class="sxs-lookup"><span data-stu-id="aa06d-107">Description</span></span>|  
|------------|-----------------|  
|`arfFullOriginator`|<span data-ttu-id="aa06d-108">어셈블리 참조 어셈블리의 게시자에 대 한 완전 한 해시 되지 않은 정보에 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa06d-108">Specifies that the assembly reference contains full, unhashed information about the publisher of the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="aa06d-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="aa06d-109">Requirements</span></span>  
 <span data-ttu-id="aa06d-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="aa06d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa06d-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="aa06d-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="aa06d-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa06d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa06d-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="aa06d-113">See also</span></span>

- [<span data-ttu-id="aa06d-114">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="aa06d-114">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="aa06d-115">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aa06d-115">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="aa06d-116">DefineAssemblyRef 메서드</span><span class="sxs-lookup"><span data-stu-id="aa06d-116">DefineAssemblyRef Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)
