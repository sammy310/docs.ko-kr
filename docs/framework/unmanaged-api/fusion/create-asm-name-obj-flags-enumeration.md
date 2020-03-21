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
ms.openlocfilehash: ee856dbd398d0fa5e3eee7d9b2b2cfc7c7a57ecf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176593"
---
# <a name="create_asm_name_obj_flags-enumeration"></a><span data-ttu-id="8c489-102">CREATE_ASM_NAME_OBJ_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="8c489-102">CREATE_ASM_NAME_OBJ_FLAGS Enumeration</span></span>
<span data-ttu-id="8c489-103">[IAssembly명 명 인터페이스](iassemblyname-interface.md) 개체가 [CreateAssemblyNameObject](createassemblynameobject-function.md) 함수에 의해 생성될 때 IAssemblyName 인터페이스 개체의 특성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8c489-103">Specifies the attributes of an [IAssemblyName Interface](iassemblyname-interface.md) object when it is constructed by the [CreateAssemblyNameObject](createassemblynameobject-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c489-104">구문</span><span class="sxs-lookup"><span data-stu-id="8c489-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
  
    CANOF_PARSE_DISPLAY_NAME            = 0x1,  
    CANOF_SET_DEFAULT_VALUES            = 0x2,  
    CANOF_VERIFY_FRIEND_ASSEMBLYNAME    = 0x4,  
    CANOF_PARSE_FRIEND_DISPLAY_NAME     =
        CANOF_PARSE_DISPLAY_NAME | CANOF_VERIFY_FRIEND_ASSEMBLYNAME  
  
} CREATE_ASM_NAME_OBJ_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="8c489-105">구성원</span><span class="sxs-lookup"><span data-stu-id="8c489-105">Members</span></span>  
  
|<span data-ttu-id="8c489-106">멤버</span><span class="sxs-lookup"><span data-stu-id="8c489-106">Member</span></span>|<span data-ttu-id="8c489-107">Description</span><span class="sxs-lookup"><span data-stu-id="8c489-107">Description</span></span>|  
|------------|-----------------|  
|`CANOF_PARSE_DISPLAY_NAME`|<span data-ttu-id="8c489-108">전달된 매개 변수가 텍스트 ID임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8c489-108">Indicates that the parameter passed is a textual identity.</span></span>|  
|`CANOF_SET_DEFAULT_VALUES`|<span data-ttu-id="8c489-109">몇 가지 기본값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8c489-109">Sets a few default values.</span></span>|  
|`CANOF_VERIFY_FRIEND_ASSEMBLYNAME`|<span data-ttu-id="8c489-110">친구 어셈블리 규칙(이름 및 공개 키만)을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8c489-110">Verifies the friend assembly rule (only name and public key).</span></span> <span data-ttu-id="8c489-111">이 멤버는 내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c489-111">This member is for internal use only.</span></span>|  
|`CANOF_PARSE_FRIEND_DISPLAY_NAME`|<span data-ttu-id="8c489-112">`CANOF_PARSE_DISPLAY_NAME` 와 `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` 플래그의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="8c489-112">A combination of the `CANOF_PARSE_DISPLAY_NAME` and `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` flags.</span></span> <span data-ttu-id="8c489-113">이 멤버는 내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c489-113">This member is for internal use only.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8c489-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8c489-114">Requirements</span></span>  
 <span data-ttu-id="8c489-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8c489-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c489-116">**헤더:** 퓨전.h</span><span class="sxs-lookup"><span data-stu-id="8c489-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="8c489-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c489-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c489-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8c489-118">See also</span></span>

- [<span data-ttu-id="8c489-119">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8c489-119">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="8c489-120">CreateAssemblyNameObject 함수</span><span class="sxs-lookup"><span data-stu-id="8c489-120">CreateAssemblyNameObject Function</span></span>](createassemblynameobject-function.md)
- [<span data-ttu-id="8c489-121">Fusion 열거형</span><span class="sxs-lookup"><span data-stu-id="8c489-121">Fusion Enumerations</span></span>](fusion-enumerations.md)
