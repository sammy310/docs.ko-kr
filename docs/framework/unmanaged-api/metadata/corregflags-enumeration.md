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
ms.openlocfilehash: d8d7a43848929e49a8cb48fb957f37213ac78f2e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007353"
---
# <a name="corregflags-enumeration"></a><span data-ttu-id="63b16-102">CorRegFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="63b16-102">CorRegFlags Enumeration</span></span>
<span data-ttu-id="63b16-103">모듈 또는 복합 이미지를 설치할 때 등록에 사용 되는 플래그 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="63b16-103">Provides flag values used for registration when installing a module or composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63b16-104">구문</span><span class="sxs-lookup"><span data-stu-id="63b16-104">Syntax</span></span>  
  
```cpp  
typedef enum
{  
    regNoCopy  = 0x00000001,  
    regConfig  = 0x00000002,  
    regHasRefs = 0x00000004  
} CorRegFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="63b16-105">멤버</span><span class="sxs-lookup"><span data-stu-id="63b16-105">Members</span></span>  
  
|<span data-ttu-id="63b16-106">멤버</span><span class="sxs-lookup"><span data-stu-id="63b16-106">Member</span></span>|<span data-ttu-id="63b16-107">설명</span><span class="sxs-lookup"><span data-stu-id="63b16-107">Description</span></span>|  
|------------|-----------------|  
|`regNoCopy`|<span data-ttu-id="63b16-108">파일이 대상에 복사 되지 않도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="63b16-108">Specifies that files should not be copied into the destination.</span></span>|  
|`regConfig`|<span data-ttu-id="63b16-109">모듈 또는 복합 구성이 구성 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="63b16-109">Specifies that the module or composite is a configuration.</span></span>|  
|`regHasRefs`|<span data-ttu-id="63b16-110">모듈 또는 복합에 클래스 참조가 있음을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="63b16-110">Specifies that the module or composite has class references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="63b16-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="63b16-111">Requirements</span></span>  
 <span data-ttu-id="63b16-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="63b16-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63b16-113">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="63b16-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="63b16-114">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="63b16-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="63b16-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63b16-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63b16-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="63b16-116">See also</span></span>

- [<span data-ttu-id="63b16-117">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="63b16-117">Metadata Enumerations</span></span>](metadata-enumerations.md)
