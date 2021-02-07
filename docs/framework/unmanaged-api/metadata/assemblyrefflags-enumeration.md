---
description: '자세한 정보: AssemblyRefFlags 열거'
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
ms.openlocfilehash: 1b33faf816194c8b386f34a63d885ba37c4329a4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678902"
---
# <a name="assemblyrefflags-enumeration"></a><span data-ttu-id="4a271-103">AssemblyRefFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="4a271-103">AssemblyRefFlags Enumeration</span></span>

<span data-ttu-id="4a271-104">어셈블리 참조의 기능을 설명 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a271-104">Contains values that describe features of an assembly reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a271-105">구문</span><span class="sxs-lookup"><span data-stu-id="4a271-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    arfFullOriginator = 0x0001  
} AssemblyRefFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="4a271-106">구성원</span><span class="sxs-lookup"><span data-stu-id="4a271-106">Members</span></span>  
  
|<span data-ttu-id="4a271-107">멤버</span><span class="sxs-lookup"><span data-stu-id="4a271-107">Member</span></span>|<span data-ttu-id="4a271-108">설명</span><span class="sxs-lookup"><span data-stu-id="4a271-108">Description</span></span>|  
|------------|-----------------|  
|`arfFullOriginator`|<span data-ttu-id="4a271-109">어셈블리 참조에 어셈블리의 게시자에 대 한 해시 되지 않은 전체 정보를 포함 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a271-109">Specifies that the assembly reference contains full, unhashed information about the publisher of the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4a271-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4a271-110">Requirements</span></span>  

 <span data-ttu-id="4a271-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4a271-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a271-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="4a271-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4a271-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a271-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a271-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4a271-114">See also</span></span>

- [<span data-ttu-id="4a271-115">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="4a271-115">Metadata Enumerations</span></span>](metadata-enumerations.md)
- [<span data-ttu-id="4a271-116">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4a271-116">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="4a271-117">DefineAssemblyRef 메서드</span><span class="sxs-lookup"><span data-stu-id="4a271-117">DefineAssemblyRef Method</span></span>](imetadataassemblyemit-defineassemblyref-method.md)
