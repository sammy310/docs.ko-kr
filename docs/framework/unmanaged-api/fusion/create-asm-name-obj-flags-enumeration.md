---
title: CREATE_ASM_NAME_OBJ_FLAGS 열거형
ms.date: 03/30/2017
api_name:
- CREATE_ASM_NAME_OBJ_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- CREATE_ASM_NAME_OBJ_FLAGS
helpviewer_keywords:
- CREATE_ASM_NAME_OBJ_FLAGS enumeration [.NET Framework fusion]
ms.assetid: a5ed2fd0-c7d2-4603-aaca-5d0caad92675
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 871ad81cd83c40d7299f39ede404e274b95b2ac0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778464"
---
# <a name="createasmnameobjflags-enumeration"></a><span data-ttu-id="e1beb-102">CREATE_ASM_NAME_OBJ_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="e1beb-102">CREATE_ASM_NAME_OBJ_FLAGS Enumeration</span></span>
<span data-ttu-id="e1beb-103">특성을 지정 하는 [IAssemblyName 인터페이스](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) 하 여 생성 될 때 개체를 [CreateAssemblyNameObject](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="e1beb-103">Specifies the attributes of an [IAssemblyName Interface](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object when it is constructed by the [CreateAssemblyNameObject](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1beb-104">구문</span><span class="sxs-lookup"><span data-stu-id="e1beb-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
  
    CANOF_PARSE_DISPLAY_NAME            = 0x1,  
    CANOF_SET_DEFAULT_VALUES            = 0x2,  
    CANOF_VERIFY_FRIEND_ASSEMBLYNAME    = 0x4,  
    CANOF_PARSE_FRIEND_DISPLAY_NAME     =   
        CANOF_PARSE_DISPLAY_NAME | CANOF_VERIFY_FRIEND_ASSEMBLYNAME  
  
} CREATE_ASM_NAME_OBJ_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="e1beb-105">멤버</span><span class="sxs-lookup"><span data-stu-id="e1beb-105">Members</span></span>  
  
|<span data-ttu-id="e1beb-106">멤버</span><span class="sxs-lookup"><span data-stu-id="e1beb-106">Member</span></span>|<span data-ttu-id="e1beb-107">Description</span><span class="sxs-lookup"><span data-stu-id="e1beb-107">Description</span></span>|  
|------------|-----------------|  
|`CANOF_PARSE_DISPLAY_NAME`|<span data-ttu-id="e1beb-108">전달 된 매개 변수 텍스트 id 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e1beb-108">Indicates that the parameter passed is a textual identity.</span></span>|  
|`CANOF_SET_DEFAULT_VALUES`|<span data-ttu-id="e1beb-109">몇 가지 기본값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e1beb-109">Sets a few default values.</span></span>|  
|`CANOF_VERIFY_FRIEND_ASSEMBLYNAME`|<span data-ttu-id="e1beb-110">Friend 어셈블리 규칙 (이름 및 공개 키만)을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e1beb-110">Verifies the friend assembly rule (only name and public key).</span></span> <span data-ttu-id="e1beb-111">이 멤버는 내부 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="e1beb-111">This member is for internal use only.</span></span>|  
|`CANOF_PARSE_FRIEND_DISPLAY_NAME`|<span data-ttu-id="e1beb-112">조합 된 `CANOF_PARSE_DISPLAY_NAME` 및 `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="e1beb-112">A combination of the `CANOF_PARSE_DISPLAY_NAME` and `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` flags.</span></span> <span data-ttu-id="e1beb-113">이 멤버는 내부 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="e1beb-113">This member is for internal use only.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e1beb-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e1beb-114">Requirements</span></span>  
 <span data-ttu-id="e1beb-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e1beb-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1beb-116">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="e1beb-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="e1beb-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1beb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1beb-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="e1beb-118">See also</span></span>

- [<span data-ttu-id="e1beb-119">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e1beb-119">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="e1beb-120">CreateAssemblyNameObject 함수</span><span class="sxs-lookup"><span data-stu-id="e1beb-120">CreateAssemblyNameObject Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md)
- [<span data-ttu-id="e1beb-121">Fusion 열거형</span><span class="sxs-lookup"><span data-stu-id="e1beb-121">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
