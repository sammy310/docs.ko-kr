---
description: '자세히 알아보기: CorNativeLinkType 열거형'
title: CorNativeLinkType 열거형
ms.date: 03/30/2017
api_name:
- CorNativeLinkType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeLinkType
helpviewer_keywords:
- CorNativeLinkType enumeration [.NET Framework metadata]
ms.assetid: 4f86ff37-2dab-4e64-819a-76b3bfe828ff
topic_type:
- apiref
ms.openlocfilehash: 40efc75a793da8b024eff3d7c2c620123eca08b2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784342"
---
# <a name="cornativelinktype-enumeration"></a><span data-ttu-id="23e25-103">CorNativeLinkType 열거형</span><span class="sxs-lookup"><span data-stu-id="23e25-103">CorNativeLinkType Enumeration</span></span>

<span data-ttu-id="23e25-104">네이티브 코드에서 연결된 형식을 나타내는 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="23e25-104">Provides values that indicate the type linked in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23e25-105">구문</span><span class="sxs-lookup"><span data-stu-id="23e25-105">Syntax</span></span>  
  
```cpp  
typedef enum
{  
    nltNone       = 1,  
    nltAnsi       = 2,  
    nltUnicode    = 3,  
    nltAuto       = 4,  
    nltOle        = 5,  
    nltMaxValue   = 7  
} CorNativeLinkType;  
```  
  
## <a name="members"></a><span data-ttu-id="23e25-106">구성원</span><span class="sxs-lookup"><span data-stu-id="23e25-106">Members</span></span>  
  
|<span data-ttu-id="23e25-107">멤버</span><span class="sxs-lookup"><span data-stu-id="23e25-107">Member</span></span>|<span data-ttu-id="23e25-108">설명</span><span class="sxs-lookup"><span data-stu-id="23e25-108">Description</span></span>|  
|------------|-----------------|  
|`nltNone`|<span data-ttu-id="23e25-109">지정 된 키워드가 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="23e25-109">Indicates that none of the keywords are specified.</span></span>|  
|`nltAnsi`|<span data-ttu-id="23e25-110">ANSI 키워드가 지정 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="23e25-110">Indicates that an ANSI keyword is specified.</span></span>|  
|`nltUnicode`|<span data-ttu-id="23e25-111">유니코드 키워드가 지정 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="23e25-111">Indicates that a Unicode keyword is specified</span></span>|  
|`nltAuto`|<span data-ttu-id="23e25-112">Auto 키워드가 지정 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="23e25-112">Indicates that an auto keyword is specified.</span></span>|  
|`nltOle`|<span data-ttu-id="23e25-113">OLE 키워드가 지정 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="23e25-113">Indicates that an OLE keyword is specified.</span></span>|  
|`nltMaxValue`|<span data-ttu-id="23e25-114">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23e25-114">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="23e25-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="23e25-115">Requirements</span></span>  

 <span data-ttu-id="23e25-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="23e25-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23e25-117">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="23e25-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="23e25-118">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23e25-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="23e25-119">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23e25-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23e25-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="23e25-120">See also</span></span>

- [<span data-ttu-id="23e25-121">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="23e25-121">Metadata Enumerations</span></span>](metadata-enumerations.md)
