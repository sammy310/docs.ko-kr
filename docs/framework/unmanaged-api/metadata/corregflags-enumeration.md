---
description: '다음에 대 한 자세한 정보: CorRegFlags 열거형'
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
ms.openlocfilehash: 534b7b4b170d1f586e967807c4cc8a9c82648e8b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753664"
---
# <a name="corregflags-enumeration"></a><span data-ttu-id="47ba2-103">CorRegFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="47ba2-103">CorRegFlags Enumeration</span></span>

<span data-ttu-id="47ba2-104">모듈 또는 복합 이미지를 설치할 때 등록에 사용 되는 플래그 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="47ba2-104">Provides flag values used for registration when installing a module or composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47ba2-105">구문</span><span class="sxs-lookup"><span data-stu-id="47ba2-105">Syntax</span></span>  
  
```cpp  
typedef enum
{  
    regNoCopy  = 0x00000001,  
    regConfig  = 0x00000002,  
    regHasRefs = 0x00000004  
} CorRegFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="47ba2-106">구성원</span><span class="sxs-lookup"><span data-stu-id="47ba2-106">Members</span></span>  
  
|<span data-ttu-id="47ba2-107">멤버</span><span class="sxs-lookup"><span data-stu-id="47ba2-107">Member</span></span>|<span data-ttu-id="47ba2-108">설명</span><span class="sxs-lookup"><span data-stu-id="47ba2-108">Description</span></span>|  
|------------|-----------------|  
|`regNoCopy`|<span data-ttu-id="47ba2-109">파일이 대상에 복사 되지 않도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="47ba2-109">Specifies that files should not be copied into the destination.</span></span>|  
|`regConfig`|<span data-ttu-id="47ba2-110">모듈 또는 복합 구성이 구성 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="47ba2-110">Specifies that the module or composite is a configuration.</span></span>|  
|`regHasRefs`|<span data-ttu-id="47ba2-111">모듈 또는 복합에 클래스 참조가 있음을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="47ba2-111">Specifies that the module or composite has class references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="47ba2-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="47ba2-112">Requirements</span></span>  

 <span data-ttu-id="47ba2-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="47ba2-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47ba2-114">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="47ba2-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="47ba2-115">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47ba2-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="47ba2-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47ba2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47ba2-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="47ba2-117">See also</span></span>

- [<span data-ttu-id="47ba2-118">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="47ba2-118">Metadata Enumerations</span></span>](metadata-enumerations.md)
