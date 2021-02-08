---
description: '자세히 알아보기: CorSymAddrKind 열거형'
title: CorSymAddrKind 열거형
ms.date: 03/30/2017
api_name:
- CorSymAddrKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymAddrKind
helpviewer_keywords:
- CorSymAddrKind enumeration [.NET Framework debugging]
ms.assetid: 3ef841c2-cade-42ee-ba34-2ef91d6d0879
topic_type:
- apiref
ms.openlocfilehash: 94ee9f3da63a33a9f4a80289dbf9b03969d37b3d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800502"
---
# <a name="corsymaddrkind-enumeration"></a><span data-ttu-id="0e589-103">CorSymAddrKind 열거형</span><span class="sxs-lookup"><span data-stu-id="0e589-103">CorSymAddrKind Enumeration</span></span>

<span data-ttu-id="0e589-104">메모리 주소의 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0e589-104">Indicates the type of memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e589-105">구문</span><span class="sxs-lookup"><span data-stu-id="0e589-105">Syntax</span></span>  
  
```cpp  
typedef enum CorSymAddrKind  
{  
    ADDR_IL_OFFSET          = 1,  
    ADDR_NATIVE_RVA         = 2,  
    ADDR_NATIVE_REGISTER    = 3,  
    ADDR_NATIVE_REGREL      = 4,  
    ADDR_NATIVE_OFFSET      = 5,  
    ADDR_NATIVE_REGREG      = 6,  
    ADDR_NATIVE_REGSTK      = 7,  
    ADDR_NATIVE_STKREG      = 8,  
    ADDR_BITFIELD           = 9,  
    ADDR_NATIVE_ISECTOFFSET = 10  
} CorSymAddrKind;  
```  
  
## <a name="members"></a><span data-ttu-id="0e589-106">구성원</span><span class="sxs-lookup"><span data-stu-id="0e589-106">Members</span></span>  
  
|<span data-ttu-id="0e589-107">멤버</span><span class="sxs-lookup"><span data-stu-id="0e589-107">Member</span></span>|<span data-ttu-id="0e589-108">설명</span><span class="sxs-lookup"><span data-stu-id="0e589-108">Description</span></span>|  
|------------|-----------------|  
|`ADDR_IL_OFFSET`|<span data-ttu-id="0e589-109">MSIL (Microsoft 중간 언어) 지역 변수 또는 매개 변수 인덱스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0e589-109">Indicates a Microsoft intermediate language (MSIL) local variable or parameter index.</span></span>|  
|`ADDR_NATIVE_RVA`|<span data-ttu-id="0e589-110">모듈에 대 한 상대 가상 주소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0e589-110">Indicates a relative virtual address into a module.</span></span>|  
|`ADDR_NATIVE_REGISTER`|<span data-ttu-id="0e589-111">CPU 레지스터를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0e589-111">Indicates a CPU register.</span></span>|  
|`ADDR_NATIVE_REGREL`|<span data-ttu-id="0e589-112">첫 번째 주소가 레지스터가 고 두 번째 주소가 오프셋 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0e589-112">Indicates that the first address is a register and the second address is an offset.</span></span>|  
|`ADDR_NATIVE_OFFSET`|<span data-ttu-id="0e589-113">기본 주소에서 오프셋을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0e589-113">Indicates an offset from a base address.</span></span>|  
|`ADDR_NATIVE_REGREG`|<span data-ttu-id="0e589-114">첫 번째 주소가 레지스터의 하위 부분이 고 두 번째 주소가 높은 부분 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0e589-114">Indicates that the first address is the low portion of a register, and the second address is the high portion.</span></span>|  
|`ADDR_NATIVE_REGSTK`|<span data-ttu-id="0e589-115">첫 번째 주소가 레지스터의 하위 부분이 고 두 번째 주소가 상위 부분이 며 세 번째 주소가 오프셋 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0e589-115">Indicates that the first address is the low portion of a register, the second is the high portion, and the third is an offset.</span></span>|  
|`ADDR_NATIVE_STKREG`|<span data-ttu-id="0e589-116">첫 번째 주소가 레지스터이 고, 두 번째 주소가 오프셋 임을 나타내며, 세 번째 주소가 레지스터의 상위 부분 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0e589-116">Indicates that the first address is a register, the second is an offset, and the third is the high portion of the register.</span></span>|  
|`ADDR_BITFIELD`|<span data-ttu-id="0e589-117">첫 번째 주소는 필드의 시작이 고 두 번째 주소는 필드 길이 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0e589-117">Indicates that the first address is the start of a field and the second address is the field length.</span></span>|  
|`ADDR_NATIVE_ISECTOFFSET`|<span data-ttu-id="0e589-118">첫 번째 주소는 섹션이 고 두 번째 주소는 오프셋 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0e589-118">Indicates that the first address is the section and the second address is an offset.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0e589-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0e589-119">Requirements</span></span>  

 <span data-ttu-id="0e589-120">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="0e589-120">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e589-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0e589-121">See also</span></span>

- [<span data-ttu-id="0e589-122">진단 기호 저장소 열거형</span><span class="sxs-lookup"><span data-stu-id="0e589-122">Diagnostics Symbol Store Enumerations</span></span>](diagnostics-symbol-store-enumerations.md)
