---
description: '다음에 대 한 자세한 정보: ImportFile 메서드'
title: ImportFile 메서드
ms.date: 03/30/2017
api_name:
- IALink.ImportFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFile
helpviewer_keywords:
- ImportFile method
ms.assetid: bcbe321f-b83a-4e9a-9f10-8d913e244dc9
topic_type:
- apiref
ms.openlocfilehash: 82c9c7de7cd739ee205dc3695ea651643d01ea3a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99718163"
---
# <a name="importfile-method"></a><span data-ttu-id="e5226-103">ImportFile 메서드</span><span class="sxs-lookup"><span data-stu-id="e5226-103">ImportFile Method</span></span>

<span data-ttu-id="e5226-104">어셈블리 및 바인딩되지 않은 모듈을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e5226-104">Imports assemblies and unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5226-105">구문</span><span class="sxs-lookup"><span data-stu-id="e5226-105">Syntax</span></span>  
  
```cpp  
HRESULT ImportFile(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5226-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e5226-106">Parameters</span></span>  

 `pszFilename`  
 <span data-ttu-id="e5226-107">가져올 파일의 정규화 된 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e5226-107">Fully qualified name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="e5226-108">어셈블리에 연결 된 파일의 이름을 바꾸는 데 사용할 수 있는 선택적 출력 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e5226-108">Optional output file name that can be used to rename the file as it is linked into the assembly.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="e5226-109">TRUE 이면 ImportTypes를 사용 합니다. 그렇지 않으면 가져오기는 수동으로 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5226-109">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="e5226-110">고유한 파일 ID가 저장 되는 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e5226-110">Pointer to token where a unique file ID will be stored.</span></span> <span data-ttu-id="e5226-111">파일은 어셈블리나 파일이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5226-111">The file can be an assembly or a file.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="e5226-112">[IMetaDataAssemblyImport 인터페이스](../metadata/imetadataassemblyimport-interface.md)에 대 한 포인터를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="e5226-112">Receives pointer to [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md).</span></span> <span data-ttu-id="e5226-113">파일이 어셈블리가 아닌 경우 NULL 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5226-113">Can be NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="e5226-114">가져온 파일 및/또는 범위 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e5226-114">Pointer to the count of files and/or scopes that have been imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e5226-115">Return Value</span><span class="sxs-lookup"><span data-stu-id="e5226-115">Return Value</span></span>  

 <span data-ttu-id="e5226-116">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5226-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5226-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e5226-117">Requirements</span></span>  

 <span data-ttu-id="e5226-118">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="e5226-118">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5226-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e5226-119">See also</span></span>

- [<span data-ttu-id="e5226-120">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e5226-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="e5226-121">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e5226-121">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="e5226-122">ALink API</span><span class="sxs-lookup"><span data-stu-id="e5226-122">ALink API</span></span>](index.md)
