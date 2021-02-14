---
description: '자세한 정보: Encoding을 Nothing으로 설정할 수 없음'
title: 인코딩은 Nothing으로 설정할 수 없음
ms.date: 07/20/2015
ms.assetid: 59f7c731-8291-4a85-bf51-c225e48cdc84
ms.openlocfilehash: 4fa9cbd9488501b5295da8d8ace41ef06a706c12
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100462997"
---
# <a name="encoding-cannot-be-set-to-nothing"></a><span data-ttu-id="3a45c-103">인코딩은 Nothing으로 설정할 수 없음</span><span class="sxs-lookup"><span data-stu-id="3a45c-103">Encoding cannot be set to Nothing</span></span>

<span data-ttu-id="3a45c-104">`encoding` 매개 변수가 `Nothing` 으로 설정되었지만 유효한 값이 필요하기 때문에 파일에서 읽거나 쓰려는 시도가 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="3a45c-104">An attempt to read from or write to a file has failed because the parameter `encoding` has been set to `Nothing` but requires a valid value.</span></span>  
  
 <span data-ttu-id="3a45c-105"><xref:System.Text.Encoding> 은 파일에 쓸 때 사용할 인코딩을 결정하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a45c-105"><xref:System.Text.Encoding> is used to determine what encoding to use when writing to a file.</span></span> <span data-ttu-id="3a45c-106">기본값은 UTF-8입니다.</span><span class="sxs-lookup"><span data-stu-id="3a45c-106">The default is UTF-8.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3a45c-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="3a45c-107">To correct this error</span></span>  
  
- <span data-ttu-id="3a45c-108">`encoding` 매개 변수에 대한 유효한 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3a45c-108">Supply a valid value for the `encoding` parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a45c-109">추가 정보</span><span class="sxs-lookup"><span data-stu-id="3a45c-109">See also</span></span>

- [<span data-ttu-id="3a45c-110">파일 인코딩</span><span class="sxs-lookup"><span data-stu-id="3a45c-110">File Encodings</span></span>](../developing-apps/programming/drives-directories-files/file-encodings.md)
- [<span data-ttu-id="3a45c-111">파일에서 읽기</span><span class="sxs-lookup"><span data-stu-id="3a45c-111">Reading from Files</span></span>](../developing-apps/programming/drives-directories-files/reading-from-files.md)
- [<span data-ttu-id="3a45c-112">파일에 쓰기</span><span class="sxs-lookup"><span data-stu-id="3a45c-112">Writing to Files</span></span>](../developing-apps/programming/drives-directories-files/writing-to-files.md)
- [<span data-ttu-id="3a45c-113">System.io.file.readalltext.</span><span class="sxs-lookup"><span data-stu-id="3a45c-113">My.Computer.FileSystem.ReadAllText</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A)
- [<span data-ttu-id="3a45c-114">My.user. WriteAllText</span><span class="sxs-lookup"><span data-stu-id="3a45c-114">My.Computer.FileSystem.WriteAllText</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A)
