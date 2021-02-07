---
description: '다음에 대 한 자세한 정보: 열거형 CREATE_ASM_NAME_OBJ_FLAGS'
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
ms.openlocfilehash: b68eed0671d57893e7ffbfbd8127c7ef872d5eb0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761202"
---
# <a name="create_asm_name_obj_flags-enumeration"></a><span data-ttu-id="5f3bd-103">CREATE_ASM_NAME_OBJ_FLAGS 열거형</span><span class="sxs-lookup"><span data-stu-id="5f3bd-103">CREATE_ASM_NAME_OBJ_FLAGS Enumeration</span></span>

<span data-ttu-id="5f3bd-104">[Createassemblynameobject](createassemblynameobject-function.md) 함수에 의해 생성 되는 경우 [IAssemblyName Interface](iassemblyname-interface.md) 개체의 특성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f3bd-104">Specifies the attributes of an [IAssemblyName Interface](iassemblyname-interface.md) object when it is constructed by the [CreateAssemblyNameObject](createassemblynameobject-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f3bd-105">구문</span><span class="sxs-lookup"><span data-stu-id="5f3bd-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
  
    CANOF_PARSE_DISPLAY_NAME            = 0x1,  
    CANOF_SET_DEFAULT_VALUES            = 0x2,  
    CANOF_VERIFY_FRIEND_ASSEMBLYNAME    = 0x4,  
    CANOF_PARSE_FRIEND_DISPLAY_NAME     =
        CANOF_PARSE_DISPLAY_NAME | CANOF_VERIFY_FRIEND_ASSEMBLYNAME  
  
} CREATE_ASM_NAME_OBJ_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="5f3bd-106">구성원</span><span class="sxs-lookup"><span data-stu-id="5f3bd-106">Members</span></span>  
  
|<span data-ttu-id="5f3bd-107">멤버</span><span class="sxs-lookup"><span data-stu-id="5f3bd-107">Member</span></span>|<span data-ttu-id="5f3bd-108">설명</span><span class="sxs-lookup"><span data-stu-id="5f3bd-108">Description</span></span>|  
|------------|-----------------|  
|`CANOF_PARSE_DISPLAY_NAME`|<span data-ttu-id="5f3bd-109">전달 된 매개 변수가 텍스트 id 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5f3bd-109">Indicates that the parameter passed is a textual identity.</span></span>|  
|`CANOF_SET_DEFAULT_VALUES`|<span data-ttu-id="5f3bd-110">몇 가지 기본값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f3bd-110">Sets a few default values.</span></span>|  
|`CANOF_VERIFY_FRIEND_ASSEMBLYNAME`|<span data-ttu-id="5f3bd-111">Friend 어셈블리 규칙 (이름 및 공개 키만)을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f3bd-111">Verifies the friend assembly rule (only name and public key).</span></span> <span data-ttu-id="5f3bd-112">이 멤버는 내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f3bd-112">This member is for internal use only.</span></span>|  
|`CANOF_PARSE_FRIEND_DISPLAY_NAME`|<span data-ttu-id="5f3bd-113">및 플래그의 조합 `CANOF_PARSE_DISPLAY_NAME` `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` 입니다.</span><span class="sxs-lookup"><span data-stu-id="5f3bd-113">A combination of the `CANOF_PARSE_DISPLAY_NAME` and `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` flags.</span></span> <span data-ttu-id="5f3bd-114">이 멤버는 내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f3bd-114">This member is for internal use only.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5f3bd-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5f3bd-115">Requirements</span></span>  

 <span data-ttu-id="5f3bd-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f3bd-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f3bd-117">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="5f3bd-117">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="5f3bd-118">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f3bd-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f3bd-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5f3bd-119">See also</span></span>

- [<span data-ttu-id="5f3bd-120">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5f3bd-120">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="5f3bd-121">CreateAssemblyNameObject 함수</span><span class="sxs-lookup"><span data-stu-id="5f3bd-121">CreateAssemblyNameObject Function</span></span>](createassemblynameobject-function.md)
- [<span data-ttu-id="5f3bd-122">Fusion 열거형</span><span class="sxs-lookup"><span data-stu-id="5f3bd-122">Fusion Enumerations</span></span>](fusion-enumerations.md)
