---
description: '자세히 알아보기: ICLRMetadataLocator 인터페이스'
title: ICLRMetadataLocator 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRMetadataLocator
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRMetadataLocator
helpviewer_keywords:
- ICLRMetadataLocator interface [.NET Framework debugging]
ms.assetid: 43c944f4-406a-4df6-981e-0eabb33dd5d0
topic_type:
- apiref
ms.openlocfilehash: 6e7fd45197294563e12da020379d1bd54b088698
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772615"
---
# <a name="iclrmetadatalocator-interface"></a><span data-ttu-id="73b34-103">ICLRMetadataLocator 인터페이스</span><span class="sxs-lookup"><span data-stu-id="73b34-103">ICLRMetadataLocator Interface</span></span>

<span data-ttu-id="73b34-104">데이터 액세스 서비스 계층에서 대상 프로세스의 어셈블리 메타 데이터를 찾는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73b34-104">Used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="73b34-105">메서드</span><span class="sxs-lookup"><span data-stu-id="73b34-105">Methods</span></span>  
  
|<span data-ttu-id="73b34-106">메서드</span><span class="sxs-lookup"><span data-stu-id="73b34-106">Method</span></span>|<span data-ttu-id="73b34-107">설명</span><span class="sxs-lookup"><span data-stu-id="73b34-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="73b34-108">GetMetadata 메서드</span><span class="sxs-lookup"><span data-stu-id="73b34-108">GetMetadata Method</span></span>](iclrmetadatalocator-getmetadata-method.md)|<span data-ttu-id="73b34-109">대상 프로세스에서 이미지의 메타 데이터를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="73b34-109">Retrieves the metadata of an image from the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73b34-110">설명</span><span class="sxs-lookup"><span data-stu-id="73b34-110">Remarks</span></span>  

 <span data-ttu-id="73b34-111">API 클라이언트(즉, 디버거)에서는 이 인터페이스를 특정 대상 프로세스에 적절하게 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73b34-111">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="73b34-112">예를 들어 라이브 프로세스에 대 한 구현은 메모리 덤프의 구현과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73b34-112">For example, the implementation for a live process would be different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73b34-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="73b34-113">Requirements</span></span>  

 <span data-ttu-id="73b34-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="73b34-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73b34-115">**헤더:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="73b34-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="73b34-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="73b34-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="73b34-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73b34-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73b34-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="73b34-118">See also</span></span>

- [<span data-ttu-id="73b34-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="73b34-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
