---
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
ms.openlocfilehash: f30307884a268008fd4d1a8de31ec5a49b6ab92d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705243"
---
# <a name="importfile-method"></a><span data-ttu-id="01f86-102">ImportFile 메서드</span><span class="sxs-lookup"><span data-stu-id="01f86-102">ImportFile Method</span></span>

<span data-ttu-id="01f86-103">어셈블리 및 바인딩되지 않은 모듈을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-103">Imports assemblies and unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01f86-104">구문</span><span class="sxs-lookup"><span data-stu-id="01f86-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="01f86-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="01f86-105">Parameters</span></span>  

 `pszFilename`  
 <span data-ttu-id="01f86-106">가져올 파일의 정규화 된 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-106">Fully qualified name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="01f86-107">어셈블리에 연결 된 파일의 이름을 바꾸는 데 사용할 수 있는 선택적 출력 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-107">Optional output file name that can be used to rename the file as it is linked into the assembly.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="01f86-108">TRUE 이면 ImportTypes를 사용 합니다. 그렇지 않으면 가져오기는 수동으로 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="01f86-109">고유한 파일 ID가 저장 되는 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-109">Pointer to token where a unique file ID will be stored.</span></span> <span data-ttu-id="01f86-110">파일은 어셈블리나 파일이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-110">The file can be an assembly or a file.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="01f86-111">[IMetaDataAssemblyImport 인터페이스](../metadata/imetadataassemblyimport-interface.md)에 대 한 포인터를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-111">Receives pointer to [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md).</span></span> <span data-ttu-id="01f86-112">파일이 어셈블리가 아닌 경우 NULL 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-112">Can be NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="01f86-113">가져온 파일 및/또는 범위 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-113">Pointer to the count of files and/or scopes that have been imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="01f86-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="01f86-114">Return Value</span></span>  

 <span data-ttu-id="01f86-115">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="01f86-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01f86-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="01f86-116">Requirements</span></span>  

 <span data-ttu-id="01f86-117">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="01f86-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01f86-118">참조</span><span class="sxs-lookup"><span data-stu-id="01f86-118">See also</span></span>

- [<span data-ttu-id="01f86-119">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="01f86-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="01f86-120">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="01f86-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="01f86-121">ALink API</span><span class="sxs-lookup"><span data-stu-id="01f86-121">ALink API</span></span>](index.md)
