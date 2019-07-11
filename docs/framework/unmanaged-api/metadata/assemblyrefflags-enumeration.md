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
ms.openlocfilehash: c402dcda79f013b19b091c6309b3d71951018a18
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776361"
---
# <a name="assemblyrefflags-enumeration"></a><span data-ttu-id="a5c4a-102">AssemblyRefFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="a5c4a-102">AssemblyRefFlags Enumeration</span></span>
<span data-ttu-id="a5c4a-103">어셈블리 참조의 기능을 설명 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5c4a-103">Contains values that describe features of an assembly reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5c4a-104">구문</span><span class="sxs-lookup"><span data-stu-id="a5c4a-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    arfFullOriginator = 0x0001  
} AssemblyRefFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="a5c4a-105">멤버</span><span class="sxs-lookup"><span data-stu-id="a5c4a-105">Members</span></span>  
  
|<span data-ttu-id="a5c4a-106">멤버</span><span class="sxs-lookup"><span data-stu-id="a5c4a-106">Member</span></span>|<span data-ttu-id="a5c4a-107">Description</span><span class="sxs-lookup"><span data-stu-id="a5c4a-107">Description</span></span>|  
|------------|-----------------|  
|`arfFullOriginator`|<span data-ttu-id="a5c4a-108">어셈블리 참조 어셈블리의 게시자에 대 한 완전 한 해시 되지 않은 정보에 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5c4a-108">Specifies that the assembly reference contains full, unhashed information about the publisher of the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a5c4a-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a5c4a-109">Requirements</span></span>  
 <span data-ttu-id="a5c4a-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a5c4a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5c4a-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a5c4a-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a5c4a-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5c4a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5c4a-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="a5c4a-113">See also</span></span>

- [<span data-ttu-id="a5c4a-114">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="a5c4a-114">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="a5c4a-115">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a5c4a-115">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="a5c4a-116">DefineAssemblyRef 메서드</span><span class="sxs-lookup"><span data-stu-id="a5c4a-116">DefineAssemblyRef Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)
