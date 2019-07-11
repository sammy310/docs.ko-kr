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
ms.openlocfilehash: a51e8c83d0949f68a41f6a4e10396adbc4f3c9c1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741895"
---
# <a name="getfiledef-method"></a><span data-ttu-id="89a88-102">GetFileDef 메서드</span><span class="sxs-lookup"><span data-stu-id="89a88-102">GetFileDef Method</span></span>
<span data-ttu-id="89a88-103">ALink에서 할당 된 토큰) (달리 메타 데이터에 사용 된 실제 FileDef 토큰을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="89a88-103">Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89a88-104">구문</span><span class="sxs-lookup"><span data-stu-id="89a88-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="89a88-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="89a88-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="89a88-106">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="89a88-106">ID of the assembly.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="89a88-107">토큰 추가 된 파일의 AddFile 메서드 또는 AddImport 메서드에서 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="89a88-107">Token of the added file as retrieved from AddFile Method or AddImport Method.</span></span>  
  
 `pScope`  
 <span data-ttu-id="89a88-108">FileDef 토큰을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="89a88-108">Receives the FileDef token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="89a88-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="89a88-109">Return Value</span></span>  
 <span data-ttu-id="89a88-110">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="89a88-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89a88-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="89a88-111">Requirements</span></span>  
 <span data-ttu-id="89a88-112">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="89a88-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89a88-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="89a88-113">See also</span></span>

- [<span data-ttu-id="89a88-114">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="89a88-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="89a88-115">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="89a88-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="89a88-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="89a88-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
