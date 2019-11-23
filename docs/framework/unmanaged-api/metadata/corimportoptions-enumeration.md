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
ms.openlocfilehash: 44d1776e2902988353ef4fd58aca20e56203b9da
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442848"
---
# <a name="corimportoptions-enumeration"></a><span data-ttu-id="ec168-102">CorImportOptions 열거형</span><span class="sxs-lookup"><span data-stu-id="ec168-102">CorImportOptions Enumeration</span></span>
<span data-ttu-id="ec168-103">현재 범위를 벗어난 어셈블리를 가져오는 중의 동작을 제어하는 플래그 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ec168-103">Contains flag values that control the behavior during importation of an assembly outside the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec168-104">구문</span><span class="sxs-lookup"><span data-stu-id="ec168-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="ec168-105">멤버</span><span class="sxs-lookup"><span data-stu-id="ec168-105">Members</span></span>  
  
|<span data-ttu-id="ec168-106">멤버</span><span class="sxs-lookup"><span data-stu-id="ec168-106">Member</span></span>|<span data-ttu-id="ec168-107">설명</span><span class="sxs-lookup"><span data-stu-id="ec168-107">Description</span></span>|  
|------------|-----------------|  
|`MDImportOptionDefault`|<span data-ttu-id="ec168-108">Indicates the default behavior, which is to skip deleted records.</span><span class="sxs-lookup"><span data-stu-id="ec168-108">Indicates the default behavior, which is to skip deleted records.</span></span>|  
|`MDImportOptionAll`|<span data-ttu-id="ec168-109">Indicates that all metadata should be enumerated.</span><span class="sxs-lookup"><span data-stu-id="ec168-109">Indicates that all metadata should be enumerated.</span></span>|  
|`MDImportOptionAllTypeDefs`|<span data-ttu-id="ec168-110">Indicates that all TypeDefs, including deleted ones, should be enumerated.</span><span class="sxs-lookup"><span data-stu-id="ec168-110">Indicates that all TypeDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllMethodDefs`|<span data-ttu-id="ec168-111">Indicates that all MethodDefs, including deleted ones, should be enumerated.</span><span class="sxs-lookup"><span data-stu-id="ec168-111">Indicates that all MethodDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllFieldDefs`|<span data-ttu-id="ec168-112">Indicates that all FieldDefs, including deleted ones, should be enumerated.</span><span class="sxs-lookup"><span data-stu-id="ec168-112">Indicates that all FieldDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllProperties`|<span data-ttu-id="ec168-113">Indicates that all PropertyDefs, including deleted ones, should be enumerated.</span><span class="sxs-lookup"><span data-stu-id="ec168-113">Indicates that all PropertyDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllEvents`|<span data-ttu-id="ec168-114">Indicates that all EventDefs, including deleted ones, should be enumerated.</span><span class="sxs-lookup"><span data-stu-id="ec168-114">Indicates that all EventDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllCustomAttributes`|<span data-ttu-id="ec168-115">Indicates that all custom attributes, including deleted ones, should be enumerated.</span><span class="sxs-lookup"><span data-stu-id="ec168-115">Indicates that all custom attributes, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllExportedTypes`|<span data-ttu-id="ec168-116">Indicates that all exported types, including deleted ones, should be enumerated.</span><span class="sxs-lookup"><span data-stu-id="ec168-116">Indicates that all exported types, including deleted ones, should be enumerated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ec168-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ec168-117">Requirements</span></span>  
 <span data-ttu-id="ec168-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ec168-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec168-119">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="ec168-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="ec168-120">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec168-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec168-121">참조</span><span class="sxs-lookup"><span data-stu-id="ec168-121">See also</span></span>

- [<span data-ttu-id="ec168-122">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="ec168-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
