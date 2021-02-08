---
description: '다음에 대 한 자세한 정보: CorOpenFlags 열거형'
title: CorOpenFlags 열거형
ms.date: 03/30/2017
api_name:
- CorOpenFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorOpenFlags
helpviewer_keywords:
- CorOpenFlags enumeration [.NET Framework metadata]
ms.assetid: e27a83b5-2698-4996-9032-1e0fed8b91ca
topic_type:
- apiref
ms.openlocfilehash: b8bc31b5c2b7ff0c7984aa92c38e96569b80d22e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784303"
---
# <a name="coropenflags-enumeration"></a><span data-ttu-id="ff13f-103">CorOpenFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="ff13f-103">CorOpenFlags Enumeration</span></span>

<span data-ttu-id="ff13f-104">매니페스트 파일을 열 때 메타데이터 동작을 제어하는 플래그 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ff13f-104">Contains flag values that control metadata behavior upon opening manifest files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff13f-105">구문</span><span class="sxs-lookup"><span data-stu-id="ff13f-105">Syntax</span></span>  
  
```cpp  
typedef enum CorOpenFlags  
{  
    ofRead              =   0x00000000,  
    ofWrite             =   0x00000001,  
    ofReadWriteMask     =   0x00000001,  
    ofCopyMemory        =   0x00000002,  
    ofCacheImage        =   0x00000004,  
    ofManifestMetadata  =   0x00000008,  
    ofReadOnly          =   0x00000010,  
    ofTakeOwnership     =   0x00000020,  
    ofCacheImage        =   0x00000004,  
    ofNoTypeLib         =   0x00000080,  
    ofNoTransform       =   0x00001000,  
    ofReserved1         =   0x00000100,  
    ofReserved2         =   0x00000200,  
    ofReserved          =   0xffffff40  
} CorOpenFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="ff13f-106">구성원</span><span class="sxs-lookup"><span data-stu-id="ff13f-106">Members</span></span>  
  
|<span data-ttu-id="ff13f-107">멤버</span><span class="sxs-lookup"><span data-stu-id="ff13f-107">Member</span></span>|<span data-ttu-id="ff13f-108">설명</span><span class="sxs-lookup"><span data-stu-id="ff13f-108">Description</span></span>|  
|------------|-----------------|  
|`ofRead`|<span data-ttu-id="ff13f-109">파일을 읽기 전용으로 열어야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ff13f-109">Indicates that the file should be opened for reading only.</span></span>|  
|`ofWrite`|<span data-ttu-id="ff13f-110">쓸 수 있도록 파일을 열어야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ff13f-110">Indicates that the file should be opened for writing.</span></span><br /><br /> <span data-ttu-id="ff13f-111">.winmd 파일을 열 때 `ofWrite` 플래그를 사용하는 경우에는 `ofNoTransform` 플래그도 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff13f-111">If you are using the `ofWrite` flag when opening a .winmd file, you should also pass the `ofNoTransform` flag.</span></span>|  
|`ofReadWriteMask`|<span data-ttu-id="ff13f-112">읽기 및 쓰기용 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="ff13f-112">A mask for reading and writing.</span></span>|  
|`ofCopyMemory`|<span data-ttu-id="ff13f-113">파일을 메모리로 읽어들여야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ff13f-113">Indicates that the file should be read into memory.</span></span> <span data-ttu-id="ff13f-114">메타데이터는 자체 복사본을 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff13f-114">Metadata should maintain its own copy.</span></span>|  
|`ofCacheImage`|<span data-ttu-id="ff13f-115">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ff13f-115">Obsolete.</span></span> <span data-ttu-id="ff13f-116">이 플래그는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff13f-116">This flag is ignored.</span></span>|  
|`ofManifestMetadata`|<span data-ttu-id="ff13f-117">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ff13f-117">Obsolete.</span></span> <span data-ttu-id="ff13f-118">이 플래그는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff13f-118">This flag is ignored.</span></span>|  
|`ofReadOnly`|<span data-ttu-id="ff13f-119">읽기 위해 파일을 열고 `QueryInterface` [IMetaDataEmit](imetadataemit-interface.md) 에 대 한 호출을 수행할 수 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ff13f-119">Indicates that the file should be opened for reading, and that a call to `QueryInterface` for an [IMetaDataEmit](imetadataemit-interface.md) cannot be made.</span></span>|  
|`ofTakeOwnership`|<span data-ttu-id="ff13f-120">메모리가 [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) 에 대 한 호출을 사용 하 여 할당 되었으며 메타 데이터에 의해 해제 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ff13f-120">Indicates that the memory was allocated using a call to [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) and will be freed by the metadata.</span></span>|  
|`ofNoTypeLib`|<span data-ttu-id="ff13f-121">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ff13f-121">Obsolete.</span></span> <span data-ttu-id="ff13f-122">이 플래그는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff13f-122">This flag is ignored.</span></span>|  
|`ofNoTransform`|<span data-ttu-id="ff13f-123">.winmd 파일의 자동 변형을 사용하지 않도록 설정해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ff13f-123">Indicates that automatic transforms of .winmd files should be disabled.</span></span> <span data-ttu-id="ff13f-124">즉, Windows 런타임 형식에서 .NET Framework 형식으로의 프로젝션을 사용하지 않도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff13f-124">In other words, the projection of a Windows Runtime type to a .NET Framework type should be disabled.</span></span> <span data-ttu-id="ff13f-125">자세한 내용은 [Windows 런타임 및 CLR-.net 및 Windows 런타임의 내부](/archive/msdn-magazine/2012/windows-8-special-issue/windows-runtime-and-the-clr-underneath-the-hood-with-net-and-the-windows-runtime)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ff13f-125">For more information, see [Windows Runtime and the CLR - Underneath the Hood with .NET and the Windows Runtime](/archive/msdn-magazine/2012/windows-8-special-issue/windows-runtime-and-the-clr-underneath-the-hood-with-net-and-the-windows-runtime).</span></span>|  
|`ofReserved1`|<span data-ttu-id="ff13f-126">내부용으로 예약된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ff13f-126">Reserved for internal use.</span></span>|  
|`ofReserved2`|<span data-ttu-id="ff13f-127">내부용으로 예약된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ff13f-127">Reserved for internal use.</span></span>|  
|`ofReserved`|<span data-ttu-id="ff13f-128">내부용으로 예약된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ff13f-128">Reserved for internal use.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ff13f-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ff13f-129">Requirements</span></span>  

 <span data-ttu-id="ff13f-130">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff13f-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff13f-131">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="ff13f-131">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="ff13f-132">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff13f-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff13f-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ff13f-133">See also</span></span>

- [<span data-ttu-id="ff13f-134">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="ff13f-134">Metadata Enumerations</span></span>](metadata-enumerations.md)
