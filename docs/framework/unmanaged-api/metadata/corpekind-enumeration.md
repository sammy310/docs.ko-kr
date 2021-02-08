---
description: '자세히 알아보기: CorPEKind 열거형'
title: CorPEKind 열거형
ms.date: 03/30/2017
api_name:
- CorPEKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPEKind
helpviewer_keywords:
- CorPEKind enumeration [.NET Framework metadata]
ms.assetid: 22dc6dea-b1b9-4982-a730-a022d586b117
topic_type:
- apiref
ms.openlocfilehash: 6d1f29a220ce9d4be4151d8eff6557fa8c693ed2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784277"
---
# <a name="corpekind-enumeration"></a><span data-ttu-id="85862-103">CorPEKind 열거형</span><span class="sxs-lookup"><span data-stu-id="85862-103">CorPEKind Enumeration</span></span>

<span data-ttu-id="85862-104">[IMetaDataImport2:: GetPEKind](imetadataimport2-getpekind-method.md)호출에서 반환 된 PE (이식 가능한 실행) 파일을 설명 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="85862-104">Contains values that describe a portable executable (PE) file, as returned from a call to [IMetaDataImport2::GetPEKind](imetadataimport2-getpekind-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85862-105">구문</span><span class="sxs-lookup"><span data-stu-id="85862-105">Syntax</span></span>  
  
```cpp  
typedef enum CorPEKind {  
  
    peNot           = 0x00000000,  
    peILonly        = 0x00000001,  
    pe32BitRequired = 0x00000002,  
    pe32Plus        = 0x00000004,  
    pe32Unmanaged   = 0x00000008,  
    pe32BitPreferred= 0x00000010  
  
} CorPEKind;  
```  
  
## <a name="members"></a><span data-ttu-id="85862-106">구성원</span><span class="sxs-lookup"><span data-stu-id="85862-106">Members</span></span>  
  
|<span data-ttu-id="85862-107">멤버</span><span class="sxs-lookup"><span data-stu-id="85862-107">Member</span></span>|<span data-ttu-id="85862-108">설명</span><span class="sxs-lookup"><span data-stu-id="85862-108">Description</span></span>|  
|------------|-----------------|  
|`peNot`|<span data-ttu-id="85862-109">PE 파일이 아님을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="85862-109">Indicates that this is not a PE file.</span></span>|  
|`peILOnly`|<span data-ttu-id="85862-110">이 PE 파일에 관리 되는 코드만 포함 되어 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="85862-110">Indicates that this PE file contains only managed code.</span></span>|  
|`pe32BitRequired`|<span data-ttu-id="85862-111">이 PE 파일에서 Win32 호출을 수행 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="85862-111">Indicates that this PE file makes Win32 calls.</span></span>|  
|`pe32Plus`|<span data-ttu-id="85862-112">이 PE 파일이 64 비트 플랫폼에서 실행 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="85862-112">Indicates that this PE file runs on a 64-bit platform.</span></span>|  
|`pe32Unmanaged`|<span data-ttu-id="85862-113">이 PE 파일이 네이티브 코드 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="85862-113">Indicates that this PE file is native code.</span></span>|  
|<span data-ttu-id="85862-114">pe32BitPreferred</span><span class="sxs-lookup"><span data-stu-id="85862-114">pe32BitPreferred</span></span>|<span data-ttu-id="85862-115">이 PE 파일이 플랫폼 중립적 이며 32 비트 환경에서 로드 되는 것을 선호 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="85862-115">Indicates that this PE file is platform-neutral and prefers to be loaded in a 32-bit environment.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85862-116">설명</span><span class="sxs-lookup"><span data-stu-id="85862-116">Remarks</span></span>  

 <span data-ttu-id="85862-117">이러한 값은 비트 조합에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85862-117">These values can be used in bitwise combinations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85862-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="85862-118">Requirements</span></span>  

 <span data-ttu-id="85862-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="85862-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85862-120">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="85862-120">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="85862-121">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85862-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85862-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="85862-122">See also</span></span>

- [<span data-ttu-id="85862-123">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="85862-123">Metadata Enumerations</span></span>](metadata-enumerations.md)
