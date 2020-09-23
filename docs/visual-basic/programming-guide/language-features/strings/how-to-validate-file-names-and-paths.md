---
title: '방법: 파일 이름 및 경로의 유효성 검사'
ms.date: 07/20/2015
helpviewer_keywords:
- file names [Visual Basic], validating
- strings [Visual Basic], validating
- Boolean values [Visual Basic]
- paths [Visual Basic], validating
ms.assetid: f673462d-57b7-4120-b13a-6a7592f7ab2c
ms.openlocfilehash: b722222ea8b8088a6b326eef27147c08f8419272
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91072654"
---
# <a name="how-to-validate-file-names-and-paths-in-visual-basic"></a><span data-ttu-id="0586b-102">방법: Visual Basic에서 파일 이름 및 경로 확인</span><span class="sxs-lookup"><span data-stu-id="0586b-102">How to: Validate File Names and Paths in Visual Basic</span></span>

<span data-ttu-id="0586b-103">이 예에서는 `Boolean` 문자열이 파일 이름 또는 경로를 나타내는지 여부를 나타내는 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0586b-103">This example returns a `Boolean` value that indicates whether a string represents a file name or path.</span></span> <span data-ttu-id="0586b-104">유효성 검사는 이름에 파일 시스템에서 허용 하지 않는 문자가 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0586b-104">The validation checks if the name contains characters that are not allowed by the file system.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0586b-105">예제</span><span class="sxs-lookup"><span data-stu-id="0586b-105">Example</span></span>  

 [!code-vb[VbVbcnRegEx#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#4)]  
  
 <span data-ttu-id="0586b-106">이 예에서는 이름에 잘못 된 콜론 또는 이름이 없는 디렉터리가 있는지 여부를 확인 하지 않으며 이름의 길이가 시스템에서 정의한 최대 길이를 초과 하는지 여부를 확인 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0586b-106">This example does not check if the name has incorrectly placed colons, or directories with no name, or if the length of the name exceeds the system-defined maximum length.</span></span> <span data-ttu-id="0586b-107">또한 지정 된 이름을 사용 하 여 응용 프로그램에 파일 시스템 리소스에 대 한 액세스 권한이 있는지 여부는 확인 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0586b-107">It also does not check if the application has permission to access the file-system resource with the specified name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0586b-108">참조</span><span class="sxs-lookup"><span data-stu-id="0586b-108">See also</span></span>

- <xref:System.IO.Path.GetInvalidPathChars%2A>
- [<span data-ttu-id="0586b-109">Visual Basic의 문자열 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="0586b-109">Validating Strings in Visual Basic</span></span>](validating-strings.md)
