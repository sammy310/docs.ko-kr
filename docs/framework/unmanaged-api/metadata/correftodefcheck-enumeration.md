---
title: CorRefToDefCheck 열거형
ms.date: 03/30/2017
api_name:
- CorRefToDefCheck
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRefToDefCheck
helpviewer_keywords:
- CorRefToDefCheck enumeration [.NET Framework metadata]
ms.assetid: f9a80f1a-55af-4459-b095-8441aae16119
topic_type:
- apiref
ms.openlocfilehash: e6c3c9b842bd823e8975661964480fd801779b2d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450128"
---
# <a name="correftodefcheck-enumeration"></a><span data-ttu-id="e9a92-102">CorRefToDefCheck 열거형</span><span class="sxs-lookup"><span data-stu-id="e9a92-102">CorRefToDefCheck Enumeration</span></span>
<span data-ttu-id="e9a92-103">코드를 최적화하기 위해 해당 정의로 변환되는 참조된 항목을 제어하는 플래그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e9a92-103">Specifies flags to control which referenced items are converted to their definitions in order to optimize the code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9a92-104">구문</span><span class="sxs-lookup"><span data-stu-id="e9a92-104">Syntax</span></span>  
  
```cpp  
typedef enum CorRefToDefCheck {  
    MDRefToDefDefault           = 0x00000003,  
    MDRefToDefAll               = 0xffffffff,  
    MDRefToDefNone              = 0x00000000,  
    MDTypeRefToDef              = 0x00000001,  
    MDMemberRefToDef            = 0x00000002  
} CorRefToDefCheck;  
```  
  
## <a name="members"></a><span data-ttu-id="e9a92-105">멤버</span><span class="sxs-lookup"><span data-stu-id="e9a92-105">Members</span></span>  
  
|<span data-ttu-id="e9a92-106">멤버</span><span class="sxs-lookup"><span data-stu-id="e9a92-106">Member</span></span>|<span data-ttu-id="e9a92-107">설명</span><span class="sxs-lookup"><span data-stu-id="e9a92-107">Description</span></span>|  
|------------|-----------------|  
|`MDRefToDefDefault`|<span data-ttu-id="e9a92-108">형식 참조 및 멤버 참조를 정의로 변환 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9a92-108">Specifies that type references and member references should be converted to definitions.</span></span> <span data-ttu-id="e9a92-109">이 값은 기본값 (`MDTypeRefToDef` &#124; `MDMemberRefToDef`)입니다.</span><span class="sxs-lookup"><span data-stu-id="e9a92-109">This is the default value (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).</span></span>|  
|`MDRefToDefAll`|<span data-ttu-id="e9a92-110">참조 되는 모든 항목을 정의로 변환 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9a92-110">Specifies that all referenced items should be converted to definitions.</span></span>|  
|`MDRefToDefNone`|<span data-ttu-id="e9a92-111">참조 되는 항목을 정의로 변환 하지 않도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9a92-111">Specifies that no referenced items should be converted to definitions.</span></span>|  
|`MDTypeRefToDef`|<span data-ttu-id="e9a92-112">형식 참조만 형식 정의로 변환 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9a92-112">Specifies that only type references should be converted to type definitions.</span></span>|  
|`MDMemberRefToDef`|<span data-ttu-id="e9a92-113">멤버 참조만 정의로 변환 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9a92-113">Specifies that only member references should be converted to definitions.</span></span> <span data-ttu-id="e9a92-114">즉, 멤버 참조는 메서드 정의 또는 필드 정의 중 하나로 변환 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9a92-114">That is, member references should be converted to either method definitions or field definitions.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e9a92-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e9a92-115">Requirements</span></span>  
 <span data-ttu-id="e9a92-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e9a92-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9a92-117">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="e9a92-117">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="e9a92-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9a92-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9a92-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e9a92-119">See also</span></span>

- [<span data-ttu-id="e9a92-120">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="e9a92-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
