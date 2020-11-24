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
ms.openlocfilehash: 42935813579d7f1d55a9f1daf9d8c6c1241f85be
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684709"
---
# <a name="getfiledef-method"></a><span data-ttu-id="277cd-102">GetFileDef 메서드</span><span class="sxs-lookup"><span data-stu-id="277cd-102">GetFileDef Method</span></span>

<span data-ttu-id="277cd-103">ALink에서 할당 된 토큰과는 반대로 메타 데이터에 사용 되는 실제 FileDef 토큰을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="277cd-103">Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="277cd-104">구문</span><span class="sxs-lookup"><span data-stu-id="277cd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="277cd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="277cd-105">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="277cd-106">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="277cd-106">ID of the assembly.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="277cd-107">AddFile Method 또는 AddImport 메서드에서 검색 된 추가 된 파일의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="277cd-107">Token of the added file as retrieved from AddFile Method or AddImport Method.</span></span>  
  
 `pScope`  
 <span data-ttu-id="277cd-108">FileDef 토큰을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="277cd-108">Receives the FileDef token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="277cd-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="277cd-109">Return Value</span></span>  

 <span data-ttu-id="277cd-110">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="277cd-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="277cd-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="277cd-111">Requirements</span></span>  

 <span data-ttu-id="277cd-112">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="277cd-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="277cd-113">참조</span><span class="sxs-lookup"><span data-stu-id="277cd-113">See also</span></span>

- [<span data-ttu-id="277cd-114">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="277cd-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="277cd-115">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="277cd-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="277cd-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="277cd-116">ALink API</span></span>](index.md)
