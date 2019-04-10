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
ms.openlocfilehash: aebc6dfe4830e6477cda8fd279b8ef2a8040895c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59149671"
---
# <a name="createasmnameobjflags-enumeration"></a><span data-ttu-id="faff7-102">CREATE_ASM_NAME_OBJ_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="faff7-102">CREATE_ASM_NAME_OBJ_FLAGS Enumeration</span></span>
<span data-ttu-id="faff7-103">특성을 지정 하는 [IAssemblyName 인터페이스](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) 하 여 생성 될 때 개체를 [CreateAssemblyNameObject](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="faff7-103">Specifies the attributes of an [IAssemblyName Interface](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object when it is constructed by the [CreateAssemblyNameObject](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="faff7-104">구문</span><span class="sxs-lookup"><span data-stu-id="faff7-104">Syntax</span></span>  
  
```  
typedef enum {  
  
    CANOF_PARSE_DISPLAY_NAME            = 0x1,  
    CANOF_SET_DEFAULT_VALUES            = 0x2,  
    CANOF_VERIFY_FRIEND_ASSEMBLYNAME    = 0x4,  
    CANOF_PARSE_FRIEND_DISPLAY_NAME     =   
        CANOF_PARSE_DISPLAY_NAME | CANOF_VERIFY_FRIEND_ASSEMBLYNAME  
  
} CREATE_ASM_NAME_OBJ_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="faff7-105">멤버</span><span class="sxs-lookup"><span data-stu-id="faff7-105">Members</span></span>  
  
|<span data-ttu-id="faff7-106">멤버</span><span class="sxs-lookup"><span data-stu-id="faff7-106">Member</span></span>|<span data-ttu-id="faff7-107">설명</span><span class="sxs-lookup"><span data-stu-id="faff7-107">Description</span></span>|  
|------------|-----------------|  
|`CANOF_PARSE_DISPLAY_NAME`|<span data-ttu-id="faff7-108">전달 된 매개 변수 텍스트 id 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="faff7-108">Indicates that the parameter passed is a textual identity.</span></span>|  
|`CANOF_SET_DEFAULT_VALUES`|<span data-ttu-id="faff7-109">몇 가지 기본값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="faff7-109">Sets a few default values.</span></span>|  
|`CANOF_VERIFY_FRIEND_ASSEMBLYNAME`|<span data-ttu-id="faff7-110">Friend 어셈블리 규칙 (이름 및 공개 키만)을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="faff7-110">Verifies the friend assembly rule (only name and public key).</span></span> <span data-ttu-id="faff7-111">이 멤버는 내부 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="faff7-111">This member is for internal use only.</span></span>|  
|`CANOF_PARSE_FRIEND_DISPLAY_NAME`|<span data-ttu-id="faff7-112">조합 된 `CANOF_PARSE_DISPLAY_NAME` 및 `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="faff7-112">A combination of the `CANOF_PARSE_DISPLAY_NAME` and `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` flags.</span></span> <span data-ttu-id="faff7-113">이 멤버는 내부 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="faff7-113">This member is for internal use only.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="faff7-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="faff7-114">Requirements</span></span>  
 <span data-ttu-id="faff7-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="faff7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="faff7-116">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="faff7-116">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="faff7-117">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="faff7-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="faff7-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="faff7-118">See also</span></span>

- [<span data-ttu-id="faff7-119">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="faff7-119">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="faff7-120">CreateAssemblyNameObject 함수</span><span class="sxs-lookup"><span data-stu-id="faff7-120">CreateAssemblyNameObject Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md)
- [<span data-ttu-id="faff7-121">Fusion 열거형</span><span class="sxs-lookup"><span data-stu-id="faff7-121">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
