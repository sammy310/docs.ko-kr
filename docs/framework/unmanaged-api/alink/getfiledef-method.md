---
title: GetFileDef 메서드
ms.date: 03/30/2017
api_name:
- IALink2.GetFileDef
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetFileDef
helpviewer_keywords:
- GetFileDef method
ms.assetid: 4e3fbe6c-b82a-4181-ab17-7faa1263f5b3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9153c9b3735e265d59ba072f747c92434c95d9ed
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59184498"
---
# <a name="getfiledef-method"></a><span data-ttu-id="3fdcb-102">GetFileDef 메서드</span><span class="sxs-lookup"><span data-stu-id="3fdcb-102">GetFileDef Method</span></span>
<span data-ttu-id="3fdcb-103">ALink에서 할당 된 토큰) (달리 메타 데이터에 사용 된 실제 FileDef 토큰을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fdcb-103">Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fdcb-104">구문</span><span class="sxs-lookup"><span data-stu-id="3fdcb-104">Syntax</span></span>  
  
```  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="3fdcb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3fdcb-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="3fdcb-106">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3fdcb-106">ID of the assembly.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="3fdcb-107">토큰 추가 된 파일의 AddFile 메서드 또는 AddImport 메서드에서 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fdcb-107">Token of the added file as retrieved from AddFile Method or AddImport Method.</span></span>  
  
 `pScope`  
 <span data-ttu-id="3fdcb-108">FileDef 토큰을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="3fdcb-108">Receives the FileDef token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3fdcb-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="3fdcb-109">Return Value</span></span>  
 <span data-ttu-id="3fdcb-110">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fdcb-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fdcb-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3fdcb-111">Requirements</span></span>  
 <span data-ttu-id="3fdcb-112">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="3fdcb-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fdcb-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="3fdcb-113">See also</span></span>

- [<span data-ttu-id="3fdcb-114">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3fdcb-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="3fdcb-115">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3fdcb-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="3fdcb-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="3fdcb-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
