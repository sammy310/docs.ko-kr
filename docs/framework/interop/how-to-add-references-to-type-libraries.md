---
title: '방법: 형식 라이브러리에 참조 추가'
description: Visual Studio에서 또는 명령줄 컴파일을 위해 형식 라이브러리에 대한 참조를 추가하는 방법을 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- type libraries
- COM interop, importing type library
ms.assetid: f5cfa6ba-cc25-4017-82cd-ba7391859113
ms.openlocfilehash: b5e58c5943eba8db7497b4db56bfbd99b17b1043
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477630"
---
# <a name="how-to-add-references-to-type-libraries"></a>방법: 형식 라이브러리에 참조 추가

Visual Studio에서는 형식 라이브러리에 참조를 추가하면 메타데이터가 포함된 interop 어셈블리를 생성합니다. 주 interop 어셈블리를 사용할 수 있는 경우 Visual Studio는 새 interop 어셈블리를 생성하기 전에 기존 어셈블리를 사용합니다.  
  
### <a name="to-add-a-reference-to-a-type-library-in-visual-studio"></a>Visual Studio에서 형식 라이브러리에 대한 참조를 추가하려면  
  
1. Windows Setup.exe 파일이 자동으로 설치를 수행하는 경우가 아니라면 컴퓨터에 COM DLL 또는 EXE 파일을 설치하세요.  
  
2. **프로젝트**, **참조 추가** 를 차례로 선택합니다.  
  
3. 참조 관리자에서 **COM** 을 선택합니다.  
  
4. 목록에서 형식 라이브러리를 선택하거나 .tlb 파일을 찾습니다.  
  
5. **확인** 을 선택합니다.  
  
6. 솔루션 탐색기에서 방금 추가한 참조에 대한 바로 가기 메뉴를 열고 **속성** 을 선택합니다.  
  
7. **속성** 창에서 **Interop 형식 포함** 속성이 **True** 로 설정되어 있는지 확인합니다. 이 경우 Visual Studio가 COM 형식에 대한 형식 정보를 실행 파일에 포함하므로 앱과 함께 주 interop 어셈블리를 배포할 필요가 없습니다.  
  
> [!NOTE]
> 메뉴 및 대화 상자 옵션은 사용 중인 Visual Studio 버전에 따라 다를 수 있습니다.  
  
### <a name="to-add-a-reference-to-a-type-library-for-command-line-compilation"></a>명령줄 컴파일용으로 형식 라이브러리에 대한 참조를 추가하려면  
  
1. [방법: 형식 라이브러리에서 Interop 어셈블리 생성](how-to-generate-interop-assemblies-from-type-libraries.md)을 참조하세요.  
  
2. interop 어셈블리 이름을 포함한 [-link(C# 컴파일러 옵션)](../../csharp/language-reference/compiler-options/inputs.md#embedinteroptypes) 또는 [-link(Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) 컴파일러 옵션을 사용하여 COM 형식에 대한 형식 정보를 실행 파일에 포함합니다.  
  
## <a name="see-also"></a>참조

- [형식 라이브러리를 어셈블리로 가져오기](importing-a-type-library-as-an-assembly.md)
- [.NET Framework에 COM 구성 요소 노출](exposing-com-components.md)
- [연습: Visual Studio에 관리되는 어셈블리의 형식 포함](../../standard/assembly/embed-types-visual-studio.md)
- [-link(C# 컴파일러 옵션)](../../csharp/language-reference/compiler-options/inputs.md#embedinteroptypes)
- [-link(Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md)
