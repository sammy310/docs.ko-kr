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
ms.openlocfilehash: 8fe6216e11a64ea182d796247d888b862b1e8377
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177935"
---
# <a name="corregflags-enumeration"></a><span data-ttu-id="7460d-102">CorRegFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="7460d-102">CorRegFlags Enumeration</span></span>
<span data-ttu-id="7460d-103">모듈 또는 복합 이미지를 설치할 때 등록에 사용되는 플래그 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7460d-103">Provides flag values used for registration when installing a module or composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7460d-104">구문</span><span class="sxs-lookup"><span data-stu-id="7460d-104">Syntax</span></span>  
  
```cpp  
typedef enum
{  
    regNoCopy  = 0x00000001,  
    regConfig  = 0x00000002,  
    regHasRefs = 0x00000004  
} CorRegFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="7460d-105">구성원</span><span class="sxs-lookup"><span data-stu-id="7460d-105">Members</span></span>  
  
|<span data-ttu-id="7460d-106">멤버</span><span class="sxs-lookup"><span data-stu-id="7460d-106">Member</span></span>|<span data-ttu-id="7460d-107">Description</span><span class="sxs-lookup"><span data-stu-id="7460d-107">Description</span></span>|  
|------------|-----------------|  
|`regNoCopy`|<span data-ttu-id="7460d-108">파일을 대상으로 복사해서는 안 되도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7460d-108">Specifies that files should not be copied into the destination.</span></span>|  
|`regConfig`|<span data-ttu-id="7460d-109">모듈 또는 복합체가 구성임을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7460d-109">Specifies that the module or composite is a configuration.</span></span>|  
|`regHasRefs`|<span data-ttu-id="7460d-110">모듈 또는 복합체에 클래스 참조가 있음을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7460d-110">Specifies that the module or composite has class references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7460d-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7460d-111">Requirements</span></span>  
 <span data-ttu-id="7460d-112">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7460d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7460d-113">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="7460d-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7460d-114">**라이브러리:** MsCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="7460d-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7460d-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7460d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7460d-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7460d-116">See also</span></span>

- [<span data-ttu-id="7460d-117">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="7460d-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
