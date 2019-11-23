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
ms.openlocfilehash: 23d293a87112c62cb2127b435faeca258a7de226
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444227"
---
# <a name="assemblyrefflags-enumeration"></a><span data-ttu-id="fae91-102">AssemblyRefFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="fae91-102">AssemblyRefFlags Enumeration</span></span>
<span data-ttu-id="fae91-103">Contains values that describe features of an assembly reference.</span><span class="sxs-lookup"><span data-stu-id="fae91-103">Contains values that describe features of an assembly reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fae91-104">구문</span><span class="sxs-lookup"><span data-stu-id="fae91-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    arfFullOriginator = 0x0001  
} AssemblyRefFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="fae91-105">멤버</span><span class="sxs-lookup"><span data-stu-id="fae91-105">Members</span></span>  
  
|<span data-ttu-id="fae91-106">멤버</span><span class="sxs-lookup"><span data-stu-id="fae91-106">Member</span></span>|<span data-ttu-id="fae91-107">설명</span><span class="sxs-lookup"><span data-stu-id="fae91-107">Description</span></span>|  
|------------|-----------------|  
|`arfFullOriginator`|<span data-ttu-id="fae91-108">Specifies that the assembly reference contains full, unhashed information about the publisher of the assembly.</span><span class="sxs-lookup"><span data-stu-id="fae91-108">Specifies that the assembly reference contains full, unhashed information about the publisher of the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fae91-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fae91-109">Requirements</span></span>  
 <span data-ttu-id="fae91-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fae91-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fae91-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fae91-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fae91-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fae91-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fae91-113">참조</span><span class="sxs-lookup"><span data-stu-id="fae91-113">See also</span></span>

- [<span data-ttu-id="fae91-114">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="fae91-114">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="fae91-115">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fae91-115">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="fae91-116">DefineAssemblyRef 메서드</span><span class="sxs-lookup"><span data-stu-id="fae91-116">DefineAssemblyRef Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)
