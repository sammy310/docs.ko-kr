---
title: EmitManifest 메서드
ms.date: 03/30/2017
api_name:
- EmitManifest
- IALink.EmitManifest
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitManifest
helpviewer_keywords:
- EmitManifest method
ms.assetid: fdebc1f3-b62e-4d9e-b775-8ccaa8ecb250
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 051b5f47db05301f3a3326a2cc4cc5cf5c8b1ec2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59137828"
---
# <a name="emitmanifest-method"></a><span data-ttu-id="2286b-102">EmitManifest 메서드</span><span class="sxs-lookup"><span data-stu-id="2286b-102">EmitManifest Method</span></span>
<span data-ttu-id="2286b-103">최종 매니페스트를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="2286b-103">Emits the final manifest.</span></span> <span data-ttu-id="2286b-104">기타 모든 파일을 가져오는 모든 옵션을 설정한 후이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="2286b-104">Call this method after importing all other files and setting all options.</span></span> <span data-ttu-id="2286b-105">바인딩되지 않은 모듈에 대 한이 메서드를 호출 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="2286b-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2286b-106">구문</span><span class="sxs-lookup"><span data-stu-id="2286b-106">Syntax</span></span>  
  
```  
HRESULT EmitManifest(  
    mdAssembly   AssemblyID,  
    DWORD*       pdwReserveSize,  
    mdAssembly*  ptkManifest  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="2286b-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2286b-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="2286b-108">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="2286b-108">ID of the assembly.</span></span>  
  
 `pdwReserveSize`  
 <span data-ttu-id="2286b-109">검색 된 어셈블리 파일에서 예약 크기를 받는 [StrongNameSignatureSize 함수](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2286b-109">Receives the size to reserve in the assembly file, retrieved from [StrongNameSignatureSize Function](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md).</span></span>  
  
 `ptkManifest`  
 <span data-ttu-id="2286b-110">필요에 따라 어셈블리 매니페스트 토큰을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="2286b-110">Optionally receives the assembly manifest token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2286b-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="2286b-111">Return Value</span></span>  
 <span data-ttu-id="2286b-112">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2286b-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2286b-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2286b-113">Requirements</span></span>  
 <span data-ttu-id="2286b-114">Alink.h가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2286b-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2286b-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="2286b-115">See also</span></span>

- [<span data-ttu-id="2286b-116">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2286b-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="2286b-117">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2286b-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="2286b-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="2286b-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
