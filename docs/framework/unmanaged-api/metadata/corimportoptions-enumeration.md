---
title: CorImportOptions 열거형
ms.date: 03/30/2017
api_name:
- CorImportOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorImportOptions
helpviewer_keywords:
- CorImportOptions enumeration [.NET Framework metadata]
ms.assetid: 4e5d03cb-97c9-4ff4-8dbd-17d94ee374d3
topic_type:
- apiref
ms.openlocfilehash: 3be8a004be752af8a8675a3499bdb6cbfd785840
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009199"
---
# <a name="corimportoptions-enumeration"></a><span data-ttu-id="f098e-102">CorImportOptions 열거형</span><span class="sxs-lookup"><span data-stu-id="f098e-102">CorImportOptions Enumeration</span></span>
<span data-ttu-id="f098e-103">현재 범위를 벗어난 어셈블리를 가져오는 중의 동작을 제어하는 플래그 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f098e-103">Contains flag values that control the behavior during importation of an assembly outside the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f098e-104">구문</span><span class="sxs-lookup"><span data-stu-id="f098e-104">Syntax</span></span>  
  
```cpp  
typedef enum CorImportOptions {  
  
    MDImportOptionDefault                = 0x00000000,  
    MDImportOptionAll                    = 0xFFFFFFFF,  
    MDImportOptionAllTypeDefs            = 0x00000001,  
    MDImportOptionAllMethodDefs          = 0x00000002,  
    MDImportOptionAllFieldDefs           = 0x00000004,  
    MDImportOptionAllProperties          = 0x00000008,  
    MDImportOptionAllEvents              = 0x00000010,  
    MDImportOptionAllCustomAttributes    = 0x00000020,  
    MDImportOptionAllExportedTypes       = 0x00000040  
  
} CorImportOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="f098e-105">멤버</span><span class="sxs-lookup"><span data-stu-id="f098e-105">Members</span></span>  
  
|<span data-ttu-id="f098e-106">멤버</span><span class="sxs-lookup"><span data-stu-id="f098e-106">Member</span></span>|<span data-ttu-id="f098e-107">설명</span><span class="sxs-lookup"><span data-stu-id="f098e-107">Description</span></span>|  
|------------|-----------------|  
|`MDImportOptionDefault`|<span data-ttu-id="f098e-108">삭제 된 레코드를 건너뛰는 기본 동작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f098e-108">Indicates the default behavior, which is to skip deleted records.</span></span>|  
|`MDImportOptionAll`|<span data-ttu-id="f098e-109">모든 메타 데이터를 열거 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f098e-109">Indicates that all metadata should be enumerated.</span></span>|  
|`MDImportOptionAllTypeDefs`|<span data-ttu-id="f098e-110">는 삭제 된 항목을 포함 하 여 모든 형식 정의를 열거 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f098e-110">Indicates that all TypeDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllMethodDefs`|<span data-ttu-id="f098e-111">는 삭제 된 항목을 포함 하 여 모든 MethodDefs을 열거 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f098e-111">Indicates that all MethodDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllFieldDefs`|<span data-ttu-id="f098e-112">는 삭제 된 항목을 포함 하 여 모든 FieldDefs을 열거 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f098e-112">Indicates that all FieldDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllProperties`|<span data-ttu-id="f098e-113">는 삭제 된 항목을 포함 하 여 모든 PropertyDefs을 열거 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f098e-113">Indicates that all PropertyDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllEvents`|<span data-ttu-id="f098e-114">는 삭제 된 항목을 포함 하 여 모든 EventDefs을 열거 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f098e-114">Indicates that all EventDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllCustomAttributes`|<span data-ttu-id="f098e-115">는 삭제 된 항목을 포함 하 여 모든 사용자 지정 특성을 열거 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f098e-115">Indicates that all custom attributes, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllExportedTypes`|<span data-ttu-id="f098e-116">는 삭제 된 형식을 포함 하 여 내보낸 모든 형식을 열거 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f098e-116">Indicates that all exported types, including deleted ones, should be enumerated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f098e-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f098e-117">Requirements</span></span>  
 <span data-ttu-id="f098e-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f098e-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f098e-119">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="f098e-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="f098e-120">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f098e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f098e-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f098e-121">See also</span></span>

- [<span data-ttu-id="f098e-122">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="f098e-122">Metadata Enumerations</span></span>](metadata-enumerations.md)
