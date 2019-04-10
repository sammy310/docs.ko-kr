---
title: CorFileMapping 열거형
ms.date: 03/30/2017
api_name:
- CorFileMapping
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFileMapping
helpviewer_keywords:
- CorFileMapping enumeration [.NET Framework metadata]
ms.assetid: 3ca41592-b8da-475a-8032-a15627730003
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a3056836d289383161f9fa538c3c6349f88b6ba6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175619"
---
# <a name="corfilemapping-enumeration"></a><span data-ttu-id="e2914-102">CorFileMapping 열거형</span><span class="sxs-lookup"><span data-stu-id="e2914-102">CorFileMapping Enumeration</span></span>
<span data-ttu-id="e2914-103">에 대 한 호출에서 반환 되는 매핑 파일의 형식을 설명 하는 값을 포함 합니다 [imetadatainfo:: Getfilemapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="e2914-103">Contains values that describe the type of file mapping that is returned from a call to the [IMetaDataInfo::GetFileMapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2914-104">구문</span><span class="sxs-lookup"><span data-stu-id="e2914-104">Syntax</span></span>  
  
```  
typedef enum CorFileMapping {  
  
    fmFlat                  =   0x0000,  
    fmExecutableImage       =   0x0001  
  
} CorFileMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="e2914-105">멤버</span><span class="sxs-lookup"><span data-stu-id="e2914-105">Members</span></span>  
  
|<span data-ttu-id="e2914-106">멤버</span><span class="sxs-lookup"><span data-stu-id="e2914-106">Member</span></span>|<span data-ttu-id="e2914-107">설명</span><span class="sxs-lookup"><span data-stu-id="e2914-107">Description</span></span>|  
|------------|-----------------|  
|`fmFlat`|<span data-ttu-id="e2914-108">파일을 데이터 파일로 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2914-108">The file is mapped as a data file.</span></span> <span data-ttu-id="e2914-109">즉, 합니다 `SEC_IMAGE` 플래그는 Microsoft Win32 전달 되지 않으므로 `CreateFileMapping` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="e2914-109">That is, the `SEC_IMAGE` flag was not passed to the Microsoft Win32 `CreateFileMapping` function.</span></span>|  
|`fmExecutableImage`|<span data-ttu-id="e2914-110">파일 중 하나를 사용 하 여 실행을 위해 매핑된 합니다 `LoadLibrary` 함수 또는 `CreateFileMapping` 함수는 `SEC_IMAGE` 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="e2914-110">The file is mapped for execution, by using either the `LoadLibrary` function or the `CreateFileMapping` function with the `SEC_IMAGE` flag.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e2914-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e2914-111">Requirements</span></span>  
 <span data-ttu-id="e2914-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e2914-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2914-113">**헤더:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="e2914-113">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="e2914-114">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="e2914-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e2914-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="e2914-115">See also</span></span>

- [<span data-ttu-id="e2914-116">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="e2914-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="e2914-117">GetFileMapping 메서드</span><span class="sxs-lookup"><span data-stu-id="e2914-117">GetFileMapping Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md)
