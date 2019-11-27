---
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
ms.openlocfilehash: ad582fc2fd1bd1d2fc9d5a0d483fdb3a51309a10
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436498"
---
# <a name="coropenflags-enumeration"></a><span data-ttu-id="c1029-102">CorOpenFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="c1029-102">CorOpenFlags Enumeration</span></span>
<span data-ttu-id="c1029-103">매니페스트 파일을 열 때 메타데이터 동작을 제어하는 플래그 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c1029-103">Contains flag values that control metadata behavior upon opening manifest files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1029-104">구문</span><span class="sxs-lookup"><span data-stu-id="c1029-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="c1029-105">멤버</span><span class="sxs-lookup"><span data-stu-id="c1029-105">Members</span></span>  
  
|<span data-ttu-id="c1029-106">멤버</span><span class="sxs-lookup"><span data-stu-id="c1029-106">Member</span></span>|<span data-ttu-id="c1029-107">설명</span><span class="sxs-lookup"><span data-stu-id="c1029-107">Description</span></span>|  
|------------|-----------------|  
|`ofRead`|<span data-ttu-id="c1029-108">파일을 읽기 전용으로 열어야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c1029-108">Indicates that the file should be opened for reading only.</span></span>|  
|`ofWrite`|<span data-ttu-id="c1029-109">쓸 수 있도록 파일을 열어야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c1029-109">Indicates that the file should be opened for writing.</span></span><br /><br /> <span data-ttu-id="c1029-110">.winmd 파일을 열 때 `ofWrite` 플래그를 사용하는 경우에는 `ofNoTransform` 플래그도 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1029-110">If you are using the `ofWrite` flag when opening a .winmd file, you should also pass the `ofNoTransform` flag.</span></span>|  
|`ofReadWriteMask`|<span data-ttu-id="c1029-111">읽기 및 쓰기용 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="c1029-111">A mask for reading and writing.</span></span>|  
|`ofCopyMemory`|<span data-ttu-id="c1029-112">파일을 메모리로 읽어들여야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c1029-112">Indicates that the file should be read into memory.</span></span> <span data-ttu-id="c1029-113">메타데이터는 자체 복사본을 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1029-113">Metadata should maintain its own copy.</span></span>|  
|`ofCacheImage`|<span data-ttu-id="c1029-114">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c1029-114">Obsolete.</span></span> <span data-ttu-id="c1029-115">이 플래그는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1029-115">This flag is ignored.</span></span>|  
|`ofManifestMetadata`|<span data-ttu-id="c1029-116">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c1029-116">Obsolete.</span></span> <span data-ttu-id="c1029-117">이 플래그는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1029-117">This flag is ignored.</span></span>|  
|`ofReadOnly`|<span data-ttu-id="c1029-118">읽기 위해 파일을 열어야 하며 [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) 에 대 한 `QueryInterface` 호출을 만들 수 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c1029-118">Indicates that the file should be opened for reading, and that a call to `QueryInterface` for an [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) cannot be made.</span></span>|  
|`ofTakeOwnership`|<span data-ttu-id="c1029-119">메모리가 [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) 에 대 한 호출을 사용 하 여 할당 되었으며 메타 데이터에 의해 해제 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c1029-119">Indicates that the memory was allocated using a call to [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) and will be freed by the metadata.</span></span>|  
|`ofNoTypeLib`|<span data-ttu-id="c1029-120">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c1029-120">Obsolete.</span></span> <span data-ttu-id="c1029-121">이 플래그는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1029-121">This flag is ignored.</span></span>|  
|`ofNoTransform`|<span data-ttu-id="c1029-122">.winmd 파일의 자동 변형을 사용하지 않도록 설정해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c1029-122">Indicates that automatic transforms of .winmd files should be disabled.</span></span> <span data-ttu-id="c1029-123">즉, Windows 런타임 형식에서 .NET Framework 형식으로의 프로젝션을 사용하지 않도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1029-123">In other words, the projection of a Windows Runtime type to a .NET Framework type should be disabled.</span></span> <span data-ttu-id="c1029-124">자세한 내용은 [Windows 런타임 및 CLR-.net 및 Windows 런타임의 내부](https://docs.microsoft.com/archive/msdn-magazine/2012/windows-8-special-issue/windows-runtime-and-the-clr-underneath-the-hood-with-net-and-the-windows-runtime)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c1029-124">For more information, see [Windows Runtime and the CLR - Underneath the Hood with .NET and the Windows Runtime](https://docs.microsoft.com/archive/msdn-magazine/2012/windows-8-special-issue/windows-runtime-and-the-clr-underneath-the-hood-with-net-and-the-windows-runtime).</span></span>|  
|`ofReserved1`|<span data-ttu-id="c1029-125">내부 용도로 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1029-125">Reserved for internal use.</span></span>|  
|`ofReserved2`|<span data-ttu-id="c1029-126">내부 용도로 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1029-126">Reserved for internal use.</span></span>|  
|`ofReserved`|<span data-ttu-id="c1029-127">내부 용도로 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1029-127">Reserved for internal use.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c1029-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c1029-128">Requirements</span></span>  
 <span data-ttu-id="c1029-129">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c1029-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1029-130">**헤더:** CorHdr .h</span><span class="sxs-lookup"><span data-stu-id="c1029-130">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="c1029-131">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1029-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1029-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c1029-132">See also</span></span>

- [<span data-ttu-id="c1029-133">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="c1029-133">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
