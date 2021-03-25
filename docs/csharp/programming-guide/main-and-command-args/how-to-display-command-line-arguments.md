---
title: 명령줄 인수를 표시하는 방법 - C# 프로그래밍 가이드
description: 명령줄 인수를 표시하는 방법을 알아봅니다. 코드 예제를 살펴보고 사용 가능한 추가 리소스를 확인합니다.
ms.date: 03/08/2021
helpviewer_keywords:
- command-line arguments [C#], displaying
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
ms.openlocfilehash: 7c3e8d7f6ad2a599308057e996808509e70b7508
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103480268"
---
# <a name="how-to-display-command-line-arguments-c-programming-guide"></a>명령줄 인수를 표시하는 방법(C# 프로그래밍 가이드)

명령줄에서 실행 파일에 제공된 인수는 [최상위 문](top-level-statements.md) 또는 `Main`에 대한 선택적 매개 변수를 통해 액세스할 수 있습니다. 인수는 문자열 배열의 형태로 제공됩니다. 배열의 각 요소에는 하나의 인수가 포함되어 있습니다. 인수 사이의 공백은 제거됩니다. 예를 들어 명령줄에서 다음과 같이 가상 실행 파일을 호출한다고 가정합니다.  
  
|명령줄 입력|Main에 전달되는 문자열 배열|  
|----------------------------|-------------------------------------|  
|**executable.exe a b c**|"a"<br /><br /> "b"<br /><br /> "c"|  
|**executable.exe one two**|"one"<br /><br /> "two"|  
|**executable.exe "one two" three**|"one two"<br /><br /> "three"|  
  
> [!NOTE]
> Visual Studio에서 애플리케이션을 실행할 경우 [프로젝트 디자이너, 디버그 페이지](/visualstudio/ide/reference/debug-page-project-designer)에서 명령줄 인수를 지정할 수 있습니다.  
  
## <a name="example"></a>예제  

 이 예제에서는 명령줄 애플리케이션에 전달된 명령줄 인수를 표시합니다. 위의 표에서 첫 번째 항목에 대한 출력이 표시됩니다.  
  
 [!code-csharp[csProgGuideMain#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class1.cs#9)]  
  
## <a name="see-also"></a>참고 항목

- [C# 프로그래밍 가이드](../index.md)
- [Main()과 명령줄 인수](./index.md)
- [Main() 반환 값](./main-return-values.md)
