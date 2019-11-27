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
ms.openlocfilehash: f85a36c810df52f871ecc75b92a3b4440455c66b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450300"
---
# <a name="corfilemapping-enumeration"></a><span data-ttu-id="1d9d1-102">CorFileMapping 열거형</span><span class="sxs-lookup"><span data-stu-id="1d9d1-102">CorFileMapping Enumeration</span></span>
<span data-ttu-id="1d9d1-103">[IMetaDataInfo:: GetFileMapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md) 메서드 호출에서 반환 되는 파일 매핑의 유형을 설명 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d9d1-103">Contains values that describe the type of file mapping that is returned from a call to the [IMetaDataInfo::GetFileMapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d9d1-104">구문</span><span class="sxs-lookup"><span data-stu-id="1d9d1-104">Syntax</span></span>  
  
```cpp  
typedef enum CorFileMapping {  
  
    fmFlat                  =   0x0000,  
    fmExecutableImage       =   0x0001  
  
} CorFileMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="1d9d1-105">멤버</span><span class="sxs-lookup"><span data-stu-id="1d9d1-105">Members</span></span>  
  
|<span data-ttu-id="1d9d1-106">멤버</span><span class="sxs-lookup"><span data-stu-id="1d9d1-106">Member</span></span>|<span data-ttu-id="1d9d1-107">설명</span><span class="sxs-lookup"><span data-stu-id="1d9d1-107">Description</span></span>|  
|------------|-----------------|  
|`fmFlat`|<span data-ttu-id="1d9d1-108">파일은 데이터 파일로 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d9d1-108">The file is mapped as a data file.</span></span> <span data-ttu-id="1d9d1-109">즉, `SEC_IMAGE` 플래그가 Microsoft Win32 `CreateFileMapping` 함수로 전달 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="1d9d1-109">That is, the `SEC_IMAGE` flag was not passed to the Microsoft Win32 `CreateFileMapping` function.</span></span>|  
|`fmExecutableImage`|<span data-ttu-id="1d9d1-110">`LoadLibrary` 함수 또는 `SEC_IMAGE` 플래그를 사용 하는 `CreateFileMapping` 함수를 사용 하 여 실행을 위해 파일이 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d9d1-110">The file is mapped for execution, by using either the `LoadLibrary` function or the `CreateFileMapping` function with the `SEC_IMAGE` flag.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1d9d1-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1d9d1-111">Requirements</span></span>  
 <span data-ttu-id="1d9d1-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d9d1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d9d1-113">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="1d9d1-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="1d9d1-114">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d9d1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d9d1-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1d9d1-115">See also</span></span>

- [<span data-ttu-id="1d9d1-116">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="1d9d1-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="1d9d1-117">GetFileMapping 메서드</span><span class="sxs-lookup"><span data-stu-id="1d9d1-117">GetFileMapping Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md)
