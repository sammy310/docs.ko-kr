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
ms.openlocfilehash: 1307f555c9d8b6d28febcf25db89ae856c143d71
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009407"
---
# <a name="assemblyrefflags-enumeration"></a><span data-ttu-id="4c901-102">AssemblyRefFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="4c901-102">AssemblyRefFlags Enumeration</span></span>
<span data-ttu-id="4c901-103">어셈블리 참조의 기능을 설명 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c901-103">Contains values that describe features of an assembly reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c901-104">구문</span><span class="sxs-lookup"><span data-stu-id="4c901-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    arfFullOriginator = 0x0001  
} AssemblyRefFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="4c901-105">멤버</span><span class="sxs-lookup"><span data-stu-id="4c901-105">Members</span></span>  
  
|<span data-ttu-id="4c901-106">멤버</span><span class="sxs-lookup"><span data-stu-id="4c901-106">Member</span></span>|<span data-ttu-id="4c901-107">설명</span><span class="sxs-lookup"><span data-stu-id="4c901-107">Description</span></span>|  
|------------|-----------------|  
|`arfFullOriginator`|<span data-ttu-id="4c901-108">어셈블리 참조에 어셈블리의 게시자에 대 한 해시 되지 않은 전체 정보를 포함 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c901-108">Specifies that the assembly reference contains full, unhashed information about the publisher of the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4c901-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4c901-109">Requirements</span></span>  
 <span data-ttu-id="4c901-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4c901-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c901-111">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="4c901-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4c901-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c901-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c901-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4c901-113">See also</span></span>

- [<span data-ttu-id="4c901-114">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="4c901-114">Metadata Enumerations</span></span>](metadata-enumerations.md)
- [<span data-ttu-id="4c901-115">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4c901-115">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="4c901-116">DefineAssemblyRef 메서드</span><span class="sxs-lookup"><span data-stu-id="4c901-116">DefineAssemblyRef Method</span></span>](imetadataassemblyemit-defineassemblyref-method.md)
