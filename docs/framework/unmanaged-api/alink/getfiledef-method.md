---
description: '자세히 알아보기: GetFileDef 메서드'
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
ms.openlocfilehash: 5d44336e686ca565f468fb95ce5290ee41d5e16e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99718449"
---
# <a name="getfiledef-method"></a><span data-ttu-id="c7357-103">GetFileDef 메서드</span><span class="sxs-lookup"><span data-stu-id="c7357-103">GetFileDef Method</span></span>

<span data-ttu-id="c7357-104">ALink에서 할당 된 토큰과는 반대로 메타 데이터에 사용 되는 실제 FileDef 토큰을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7357-104">Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7357-105">구문</span><span class="sxs-lookup"><span data-stu-id="c7357-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7357-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c7357-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="c7357-107">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c7357-107">ID of the assembly.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="c7357-108">AddFile Method 또는 AddImport 메서드에서 검색 된 추가 된 파일의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="c7357-108">Token of the added file as retrieved from AddFile Method or AddImport Method.</span></span>  
  
 `pScope`  
 <span data-ttu-id="c7357-109">FileDef 토큰을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="c7357-109">Receives the FileDef token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c7357-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="c7357-110">Return Value</span></span>  

 <span data-ttu-id="c7357-111">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7357-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7357-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c7357-112">Requirements</span></span>  

 <span data-ttu-id="c7357-113">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="c7357-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7357-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c7357-114">See also</span></span>

- [<span data-ttu-id="c7357-115">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c7357-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="c7357-116">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c7357-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="c7357-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="c7357-117">ALink API</span></span>](index.md)
