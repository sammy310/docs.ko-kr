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
ms.openlocfilehash: 5ea588194720394ad9f361fbba702f3fcdcbe110
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706101"
---
# <a name="corregflags-enumeration"></a><span data-ttu-id="793c0-102">CorRegFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="793c0-102">CorRegFlags Enumeration</span></span>

<span data-ttu-id="793c0-103">모듈 또는 복합 이미지를 설치할 때 등록에 사용 되는 플래그 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="793c0-103">Provides flag values used for registration when installing a module or composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="793c0-104">구문</span><span class="sxs-lookup"><span data-stu-id="793c0-104">Syntax</span></span>  
  
```cpp  
typedef enum
{  
    regNoCopy  = 0x00000001,  
    regConfig  = 0x00000002,  
    regHasRefs = 0x00000004  
} CorRegFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="793c0-105">멤버</span><span class="sxs-lookup"><span data-stu-id="793c0-105">Members</span></span>  
  
|<span data-ttu-id="793c0-106">멤버</span><span class="sxs-lookup"><span data-stu-id="793c0-106">Member</span></span>|<span data-ttu-id="793c0-107">설명</span><span class="sxs-lookup"><span data-stu-id="793c0-107">Description</span></span>|  
|------------|-----------------|  
|`regNoCopy`|<span data-ttu-id="793c0-108">파일이 대상에 복사 되지 않도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="793c0-108">Specifies that files should not be copied into the destination.</span></span>|  
|`regConfig`|<span data-ttu-id="793c0-109">모듈 또는 복합 구성이 구성 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="793c0-109">Specifies that the module or composite is a configuration.</span></span>|  
|`regHasRefs`|<span data-ttu-id="793c0-110">모듈 또는 복합에 클래스 참조가 있음을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="793c0-110">Specifies that the module or composite has class references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="793c0-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="793c0-111">Requirements</span></span>  

 <span data-ttu-id="793c0-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="793c0-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="793c0-113">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="793c0-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="793c0-114">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="793c0-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="793c0-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="793c0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="793c0-116">참조</span><span class="sxs-lookup"><span data-stu-id="793c0-116">See also</span></span>

- [<span data-ttu-id="793c0-117">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="793c0-117">Metadata Enumerations</span></span>](metadata-enumerations.md)
