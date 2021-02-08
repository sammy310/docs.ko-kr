---
description: '자세히 알아보기: CorImportOptions 열거형'
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
ms.openlocfilehash: b942ed3f5b1b3c400b4f901e3dd3c4364e1d588c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784446"
---
# <a name="corimportoptions-enumeration"></a><span data-ttu-id="1e377-103">CorImportOptions 열거형</span><span class="sxs-lookup"><span data-stu-id="1e377-103">CorImportOptions Enumeration</span></span>

<span data-ttu-id="1e377-104">현재 범위를 벗어난 어셈블리를 가져오는 중의 동작을 제어하는 플래그 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1e377-104">Contains flag values that control the behavior during importation of an assembly outside the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e377-105">구문</span><span class="sxs-lookup"><span data-stu-id="1e377-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="1e377-106">구성원</span><span class="sxs-lookup"><span data-stu-id="1e377-106">Members</span></span>  
  
|<span data-ttu-id="1e377-107">멤버</span><span class="sxs-lookup"><span data-stu-id="1e377-107">Member</span></span>|<span data-ttu-id="1e377-108">설명</span><span class="sxs-lookup"><span data-stu-id="1e377-108">Description</span></span>|  
|------------|-----------------|  
|`MDImportOptionDefault`|<span data-ttu-id="1e377-109">삭제 된 레코드를 건너뛰는 기본 동작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1e377-109">Indicates the default behavior, which is to skip deleted records.</span></span>|  
|`MDImportOptionAll`|<span data-ttu-id="1e377-110">모든 메타 데이터를 열거 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1e377-110">Indicates that all metadata should be enumerated.</span></span>|  
|`MDImportOptionAllTypeDefs`|<span data-ttu-id="1e377-111">는 삭제 된 항목을 포함 하 여 모든 형식 정의를 열거 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1e377-111">Indicates that all TypeDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllMethodDefs`|<span data-ttu-id="1e377-112">는 삭제 된 항목을 포함 하 여 모든 MethodDefs을 열거 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1e377-112">Indicates that all MethodDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllFieldDefs`|<span data-ttu-id="1e377-113">는 삭제 된 항목을 포함 하 여 모든 FieldDefs을 열거 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1e377-113">Indicates that all FieldDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllProperties`|<span data-ttu-id="1e377-114">는 삭제 된 항목을 포함 하 여 모든 PropertyDefs을 열거 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1e377-114">Indicates that all PropertyDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllEvents`|<span data-ttu-id="1e377-115">는 삭제 된 항목을 포함 하 여 모든 EventDefs을 열거 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1e377-115">Indicates that all EventDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllCustomAttributes`|<span data-ttu-id="1e377-116">는 삭제 된 항목을 포함 하 여 모든 사용자 지정 특성을 열거 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1e377-116">Indicates that all custom attributes, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllExportedTypes`|<span data-ttu-id="1e377-117">는 삭제 된 형식을 포함 하 여 내보낸 모든 형식을 열거 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1e377-117">Indicates that all exported types, including deleted ones, should be enumerated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1e377-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1e377-118">Requirements</span></span>  

 <span data-ttu-id="1e377-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1e377-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e377-120">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="1e377-120">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="1e377-121">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e377-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e377-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1e377-122">See also</span></span>

- [<span data-ttu-id="1e377-123">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="1e377-123">Metadata Enumerations</span></span>](metadata-enumerations.md)
