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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: eb6b303fa7569712c854e8dc4e7513d8608e2519
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59104964"
---
# <a name="corregflags-enumeration"></a><span data-ttu-id="d79b2-102">CorRegFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="d79b2-102">CorRegFlags Enumeration</span></span>
<span data-ttu-id="d79b2-103">모듈 또는 합성 이미지를 설치 하는 경우 등록에 사용 되는 플래그 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d79b2-103">Provides flag values used for registration when installing a module or composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d79b2-104">구문</span><span class="sxs-lookup"><span data-stu-id="d79b2-104">Syntax</span></span>  
  
```  
typedef enum   
{  
    regNoCopy  = 0x00000001,  
    regConfig  = 0x00000002,  
    regHasRefs = 0x00000004  
} CorRegFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="d79b2-105">멤버</span><span class="sxs-lookup"><span data-stu-id="d79b2-105">Members</span></span>  
  
|<span data-ttu-id="d79b2-106">멤버</span><span class="sxs-lookup"><span data-stu-id="d79b2-106">Member</span></span>|<span data-ttu-id="d79b2-107">설명</span><span class="sxs-lookup"><span data-stu-id="d79b2-107">Description</span></span>|  
|------------|-----------------|  
|`regNoCopy`|<span data-ttu-id="d79b2-108">파일을 대상으로 복사할 해야 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d79b2-108">Specifies that files should not be copied into the destination.</span></span>|  
|`regConfig`|<span data-ttu-id="d79b2-109">구성 모듈 또는 합성 수 인지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d79b2-109">Specifies that the module or composite is a configuration.</span></span>|  
|`regHasRefs`|<span data-ttu-id="d79b2-110">모듈 또는 composite 클래스 참조에 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d79b2-110">Specifies that the module or composite has class references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d79b2-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d79b2-111">Requirements</span></span>  
 <span data-ttu-id="d79b2-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d79b2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d79b2-113">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d79b2-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d79b2-114">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="d79b2-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="d79b2-115">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="d79b2-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d79b2-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="d79b2-116">See also</span></span>

- [<span data-ttu-id="d79b2-117">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="d79b2-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
