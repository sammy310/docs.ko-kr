---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d8f830ca7e273b65dc9ec77566a02df6c32cd464
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59202393"
---
# <a name="corpekind-enumeration"></a><span data-ttu-id="ede4a-102">CorPEKind 열거형</span><span class="sxs-lookup"><span data-stu-id="ede4a-102">CorPEKind Enumeration</span></span>
<span data-ttu-id="ede4a-103">에 대 한 호출에서 반환 된 pe (이식 가능) 파일을 설명 하는 값을 포함 [IMetaDataImport2::GetPEKind](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ede4a-103">Contains values that describe a portable executable (PE) file, as returned from a call to [IMetaDataImport2::GetPEKind](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ede4a-104">구문</span><span class="sxs-lookup"><span data-stu-id="ede4a-104">Syntax</span></span>  
  
```  
typedef enum CorPEKind {  
  
    peNot           = 0x00000000,  
    peILonly        = 0x00000001,  
    pe32BitRequired = 0x00000002,  
    pe32Plus        = 0x00000004,  
    pe32Unmanaged   = 0x00000008,  
    pe32BitPreferred= 0x00000010  
  
} CorPEKind;  
```  
  
## <a name="members"></a><span data-ttu-id="ede4a-105">멤버</span><span class="sxs-lookup"><span data-stu-id="ede4a-105">Members</span></span>  
  
|<span data-ttu-id="ede4a-106">멤버</span><span class="sxs-lookup"><span data-stu-id="ede4a-106">Member</span></span>|<span data-ttu-id="ede4a-107">설명</span><span class="sxs-lookup"><span data-stu-id="ede4a-107">Description</span></span>|  
|------------|-----------------|  
|`peNot`|<span data-ttu-id="ede4a-108">PE 파일 아님을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ede4a-108">Indicates that this is not a PE file.</span></span>|  
|`peILOnly`|<span data-ttu-id="ede4a-109">이 PE 파일에 코드를 관리 되는 포함 되어 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ede4a-109">Indicates that this PE file contains only managed code.</span></span>|  
|`pe32BitRequired`|<span data-ttu-id="ede4a-110">PE 파일이 Win32 호출을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ede4a-110">Indicates that this PE file makes Win32 calls.</span></span>|  
|`pe32Plus`|<span data-ttu-id="ede4a-111">64 비트 플랫폼에서이 PE 파일을 실행 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ede4a-111">Indicates that this PE file runs on a 64-bit platform.</span></span>|  
|`pe32Unmanaged`|<span data-ttu-id="ede4a-112">PE 파일을 네이티브 코드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ede4a-112">Indicates that this PE file is native code.</span></span>|  
|<span data-ttu-id="ede4a-113">pe32BitPreferred</span><span class="sxs-lookup"><span data-stu-id="ede4a-113">pe32BitPreferred</span></span>|<span data-ttu-id="ede4a-114">PE 파일에이 플랫폼 중립적 선호 하는 32 비트 환경에서 로드할 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ede4a-114">Indicates that this PE file is platform-neutral and prefers to be loaded in a 32-bit environment.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ede4a-115">설명</span><span class="sxs-lookup"><span data-stu-id="ede4a-115">Remarks</span></span>  
 <span data-ttu-id="ede4a-116">이러한 값의 비트 조합을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ede4a-116">These values can be used in bitwise combinations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ede4a-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ede4a-117">Requirements</span></span>  
 <span data-ttu-id="ede4a-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ede4a-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ede4a-119">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="ede4a-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="ede4a-120">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ede4a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ede4a-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="ede4a-121">See also</span></span>

- [<span data-ttu-id="ede4a-122">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="ede4a-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
