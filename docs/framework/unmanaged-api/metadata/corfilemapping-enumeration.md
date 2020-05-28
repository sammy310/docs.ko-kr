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
ms.openlocfilehash: 0ed1579886f1682348a136be3391f6bdc2543d26
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007392"
---
# <a name="corfilemapping-enumeration"></a><span data-ttu-id="bc751-102">CorFileMapping 열거형</span><span class="sxs-lookup"><span data-stu-id="bc751-102">CorFileMapping Enumeration</span></span>
<span data-ttu-id="bc751-103">[IMetaDataInfo:: GetFileMapping](imetadatainfo-getfilemapping-method.md) 메서드 호출에서 반환 되는 파일 매핑의 유형을 설명 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc751-103">Contains values that describe the type of file mapping that is returned from a call to the [IMetaDataInfo::GetFileMapping](imetadatainfo-getfilemapping-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc751-104">구문</span><span class="sxs-lookup"><span data-stu-id="bc751-104">Syntax</span></span>  
  
```cpp  
typedef enum CorFileMapping {  
  
    fmFlat                  =   0x0000,  
    fmExecutableImage       =   0x0001  
  
} CorFileMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="bc751-105">멤버</span><span class="sxs-lookup"><span data-stu-id="bc751-105">Members</span></span>  
  
|<span data-ttu-id="bc751-106">멤버</span><span class="sxs-lookup"><span data-stu-id="bc751-106">Member</span></span>|<span data-ttu-id="bc751-107">설명</span><span class="sxs-lookup"><span data-stu-id="bc751-107">Description</span></span>|  
|------------|-----------------|  
|`fmFlat`|<span data-ttu-id="bc751-108">파일은 데이터 파일로 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc751-108">The file is mapped as a data file.</span></span> <span data-ttu-id="bc751-109">즉, `SEC_IMAGE` 플래그가 Microsoft Win32 함수에 전달 되지 않았습니다 `CreateFileMapping` .</span><span class="sxs-lookup"><span data-stu-id="bc751-109">That is, the `SEC_IMAGE` flag was not passed to the Microsoft Win32 `CreateFileMapping` function.</span></span>|  
|`fmExecutableImage`|<span data-ttu-id="bc751-110">파일은 플래그를 사용 하 여 함수 또는 함수를 사용 하 여 실행을 위해 매핑됩니다 `LoadLibrary` `CreateFileMapping` `SEC_IMAGE` .</span><span class="sxs-lookup"><span data-stu-id="bc751-110">The file is mapped for execution, by using either the `LoadLibrary` function or the `CreateFileMapping` function with the `SEC_IMAGE` flag.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bc751-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bc751-111">Requirements</span></span>  
 <span data-ttu-id="bc751-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bc751-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc751-113">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="bc751-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="bc751-114">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc751-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc751-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bc751-115">See also</span></span>

- [<span data-ttu-id="bc751-116">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="bc751-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
- [<span data-ttu-id="bc751-117">GetFileMapping 메서드</span><span class="sxs-lookup"><span data-stu-id="bc751-117">GetFileMapping Method</span></span>](imetadatainfo-getfilemapping-method.md)
