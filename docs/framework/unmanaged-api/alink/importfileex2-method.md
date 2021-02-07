---
description: '자세히 알아보기: ImportFileEx2 메서드'
title: ImportFileEx2 메서드
ms.date: 03/30/2017
api_name:
- IALink2.ImportFileEx2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFileEx2
helpviewer_keywords:
- ImportFileEx2 method
ms.assetid: 02c789fd-16fc-48c6-9619-56e87e2a37ca
topic_type:
- apiref
ms.openlocfilehash: 0968318ab7e416e56b71f2f30f2745d538d0ff8a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99718007"
---
# <a name="importfileex2-method"></a><span data-ttu-id="3313d-103">ImportFileEx2 메서드</span><span class="sxs-lookup"><span data-stu-id="3313d-103">ImportFileEx2 Method</span></span>

<span data-ttu-id="3313d-104">어셈블리 및 바인딩되지 않은 모듈을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3313d-104">Imports assemblies and unbound modules.</span></span> <span data-ttu-id="3313d-105">이 메서드는 [Importfile 메서드와](importfile-method.md)유사 하지만, 가져오는 파일이 디스크에 존재 하지 않는 경우에도 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3313d-105">This method is like [ImportFile Method](importfile-method.md), but works even if the file being imported does not exist on disk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3313d-106">구문</span><span class="sxs-lookup"><span data-stu-id="3313d-106">Syntax</span></span>  
  
```cpp  
HRESULT ImportFileEx2(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    IMetaDataAssemblyImport* pAssemblyScopeIn,  
    BOOL fSmartImport,  
    DWORD dwOpenFlags,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="3313d-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3313d-107">Parameters</span></span>  

 `pszFilename`  
 <span data-ttu-id="3313d-108">가져올 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3313d-108">Name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="3313d-109">대상 파일의 선택적 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3313d-109">Optional name of target file.</span></span>  
  
 `pAssemblyScopeIn`  
 <span data-ttu-id="3313d-110">선택적 가져오기 범위 [IMetaDataAssemblyImport interface](../metadata/imetadataassemblyimport-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="3313d-110">Optional import scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="3313d-111">TRUE 이면 ImportTypes를 사용 합니다. 그렇지 않으면 가져오기는 수동으로 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3313d-111">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="3313d-112">[Openscope 메서드에](../metadata/imetadatadispenser-openscope-method.md)따라 전달할 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="3313d-112">Flags to be passed along to [OpenScope Method](../metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="3313d-113">어셈블리나 파일의 고유 ID를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="3313d-113">Receives unique ID for the assembly or file.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="3313d-114">어셈블리 가져오기 범위 [IMetaDataAssemblyImport interface](../metadata/imetadataassemblyimport-interface.md) 인터페이스를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="3313d-114">Receives assembly import scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="3313d-115">파일이 어셈블리가 아닌 경우 NULL 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3313d-115">Can be NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="3313d-116">가져온 파일 및/또는 범위의 수를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="3313d-116">Receives the number of files and/or scopes imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3313d-117">Return Value</span><span class="sxs-lookup"><span data-stu-id="3313d-117">Return Value</span></span>  

 <span data-ttu-id="3313d-118">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3313d-118">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3313d-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3313d-119">Requirements</span></span>  

 <span data-ttu-id="3313d-120">Alink가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3313d-120">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3313d-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3313d-121">See also</span></span>

- [<span data-ttu-id="3313d-122">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3313d-122">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="3313d-123">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3313d-123">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="3313d-124">ALink API</span><span class="sxs-lookup"><span data-stu-id="3313d-124">ALink API</span></span>](index.md)
