---
description: '자세히 알아보기: CorFileMapping 열거형'
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
ms.openlocfilehash: 0fc3916e75c576a6b133ba8a49c00eec6c9bac19
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784472"
---
# <a name="corfilemapping-enumeration"></a><span data-ttu-id="42b15-103">CorFileMapping 열거형</span><span class="sxs-lookup"><span data-stu-id="42b15-103">CorFileMapping Enumeration</span></span>

<span data-ttu-id="42b15-104">[IMetaDataInfo:: GetFileMapping](imetadatainfo-getfilemapping-method.md) 메서드 호출에서 반환 되는 파일 매핑의 유형을 설명 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="42b15-104">Contains values that describe the type of file mapping that is returned from a call to the [IMetaDataInfo::GetFileMapping](imetadatainfo-getfilemapping-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42b15-105">구문</span><span class="sxs-lookup"><span data-stu-id="42b15-105">Syntax</span></span>  
  
```cpp  
typedef enum CorFileMapping {  
  
    fmFlat                  =   0x0000,  
    fmExecutableImage       =   0x0001  
  
} CorFileMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="42b15-106">구성원</span><span class="sxs-lookup"><span data-stu-id="42b15-106">Members</span></span>  
  
|<span data-ttu-id="42b15-107">멤버</span><span class="sxs-lookup"><span data-stu-id="42b15-107">Member</span></span>|<span data-ttu-id="42b15-108">설명</span><span class="sxs-lookup"><span data-stu-id="42b15-108">Description</span></span>|  
|------------|-----------------|  
|`fmFlat`|<span data-ttu-id="42b15-109">파일은 데이터 파일로 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="42b15-109">The file is mapped as a data file.</span></span> <span data-ttu-id="42b15-110">즉, `SEC_IMAGE` 플래그가 Microsoft Win32 함수에 전달 되지 않았습니다 `CreateFileMapping` .</span><span class="sxs-lookup"><span data-stu-id="42b15-110">That is, the `SEC_IMAGE` flag was not passed to the Microsoft Win32 `CreateFileMapping` function.</span></span>|  
|`fmExecutableImage`|<span data-ttu-id="42b15-111">파일은 플래그를 사용 하 여 함수 또는 함수를 사용 하 여 실행을 위해 매핑됩니다 `LoadLibrary` `CreateFileMapping` `SEC_IMAGE` .</span><span class="sxs-lookup"><span data-stu-id="42b15-111">The file is mapped for execution, by using either the `LoadLibrary` function or the `CreateFileMapping` function with the `SEC_IMAGE` flag.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="42b15-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="42b15-112">Requirements</span></span>  

 <span data-ttu-id="42b15-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="42b15-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42b15-114">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="42b15-114">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="42b15-115">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42b15-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42b15-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="42b15-116">See also</span></span>

- [<span data-ttu-id="42b15-117">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="42b15-117">Metadata Enumerations</span></span>](metadata-enumerations.md)
- [<span data-ttu-id="42b15-118">GetFileMapping 메서드</span><span class="sxs-lookup"><span data-stu-id="42b15-118">GetFileMapping Method</span></span>](imetadatainfo-getfilemapping-method.md)
