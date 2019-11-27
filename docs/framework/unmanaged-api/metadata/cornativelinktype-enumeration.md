---
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
ms.openlocfilehash: 718e41e16c07265d8a36b8f6124d99cd3490f7be
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436621"
---
# <a name="cornativelinktype-enumeration"></a><span data-ttu-id="1e343-102">CorNativeLinkType 열거형</span><span class="sxs-lookup"><span data-stu-id="1e343-102">CorNativeLinkType Enumeration</span></span>
<span data-ttu-id="1e343-103">네이티브 코드에서 연결된 형식을 나타내는 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1e343-103">Provides values that indicate the type linked in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e343-104">구문</span><span class="sxs-lookup"><span data-stu-id="1e343-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="1e343-105">멤버</span><span class="sxs-lookup"><span data-stu-id="1e343-105">Members</span></span>  
  
|<span data-ttu-id="1e343-106">멤버</span><span class="sxs-lookup"><span data-stu-id="1e343-106">Member</span></span>|<span data-ttu-id="1e343-107">설명</span><span class="sxs-lookup"><span data-stu-id="1e343-107">Description</span></span>|  
|------------|-----------------|  
|`nltNone`|<span data-ttu-id="1e343-108">지정 된 키워드가 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1e343-108">Indicates that none of the keywords are specified.</span></span>|  
|`nltAnsi`|<span data-ttu-id="1e343-109">ANSI 키워드가 지정 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1e343-109">Indicates that an ANSI keyword is specified.</span></span>|  
|`nltUnicode`|<span data-ttu-id="1e343-110">유니코드 키워드가 지정 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1e343-110">Indicates that a Unicode keyword is specified</span></span>|  
|`nltAuto`|<span data-ttu-id="1e343-111">Auto 키워드가 지정 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1e343-111">Indicates that an auto keyword is specified.</span></span>|  
|`nltOle`|<span data-ttu-id="1e343-112">OLE 키워드가 지정 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1e343-112">Indicates that an OLE keyword is specified.</span></span>|  
|`nltMaxValue`|<span data-ttu-id="1e343-113">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e343-113">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1e343-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1e343-114">Requirements</span></span>  
 <span data-ttu-id="1e343-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1e343-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e343-116">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="1e343-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1e343-117">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e343-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1e343-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e343-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e343-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1e343-119">See also</span></span>

- [<span data-ttu-id="1e343-120">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="1e343-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
