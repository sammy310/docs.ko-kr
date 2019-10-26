---
title: LINQ to XML 데이터 바인딩 예제
ms.date: 10/22/2019
ms.topic: sample
helpviewer_keywords:
- linq to xml data binding sample
ms.openlocfilehash: aac814e4768a863a93e69e34cd18c941a9b35c89
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/25/2019
ms.locfileid: "72921223"
---
# <a name="linq-to-xml-data-binding-sample"></a>LINQ to XML 데이터 바인딩 샘플

이 문서에서는 사용자 인터페이스 구성 요소를 포함 된 XML 데이터 소스에 바인딩하는 WPF (Windows Presentation Foundation) 앱 인 LinqToXmlDataBinding 샘플에 대해 설명 합니다.

## <a name="overview"></a>개요

LinqToXmlDataBinding 샘플은 및 XAML 소스 파일을 포함 C# 하는 WPF (Windows Presentation Foundation) 앱입니다. 포함 된 XML 문서는 책 목록을 정의 합니다. 앱을 통해 사용자는 책 항목을 보고, 추가 하 고, 삭제 하 고, 편집할 수 있습니다.

기본 소스 파일은 다음 두 가지입니다.

- [L2DBForm.xaml](l2dbform-xaml-source-code.md)에는 기본 창의 UI(사용자 인터페이스)에 대한 XAML 선언 코드가 포함되어 있습니다. 또한 책 목록에 대 한 포함 된 XML 문서 및 데이터 공급자를 정의 하는 창 리소스 섹션도 포함 되어 있습니다.

- [L2DBForm.xaml.cs](l2dbform-xaml-cs-source-code.md)에는 UI와 연결된 초기화 및 이벤트 처리 메서드가 포함되어 있습니다.

기본 창은 다음 네 가지 세로 UI 섹션으로 나뉩니다.

- **XML**에서는 포함된 책 목록의 원시 XML 원본이 표시됩니다.

- **Book List**에서는 책 항목이 표준 텍스트로 표시되고 사용자가 개별 항목을 선택하고 삭제할 수 있습니다.

- **Edit Selected Book**에서는 사용자가 현재 선택된 책 항목과 연결된 값을 편집할 수 있습니다.

- **Add New Book**에서는 사용자가 입력한 값에 따라 새 책 항목을 만들 수 있습니다.

## <a name="run-the-sample"></a>샘플 실행

이 섹션에서는 Visual Studio에서 LinqToXmlDataBinding 프로젝트를 만들고 빌드하는 방법과 결과로 생성 되는 WPF (LinqToXmlDataBinding Windows Presentation Foundation) 앱을 실행 하는 방법을 보여 줍니다.

### <a name="create-the-project"></a>프로젝트를 만듭니다.

1. Visual Studio를 열고 이름이 **LinqToXmlDataBinding**인 C# **WPF 앱**을 만듭니다.

   프로젝트는 .NET Framework 3.5 이상을 대상으로 지정해야 합니다.

1. 이미 존재하지 않는 경우 다음 .NET 어셈블리에 대한 프로젝트 참조를 추가합니다.

    - System.Data
    - System.Data.DataSetExtensions
    - System.Xml
    - System.Xml

1. **Ctnrl**+**Shift**+**B**를 눌러 솔루션을 빌드한 다음, **F5**를 눌러 솔루션을 실행합니다.

   프로젝트가 오류 없이 컴파일되고 일반 WPF 애플리케이션으로 실행됩니다.

### <a name="add-code"></a>코드 추가

1. **솔루션 탐색기**에서 소스 파일 **Window1.xaml**의 이름을 **L2XDBForm.xaml**로 바꿉니다.

   종속 원본 파일 Window1.xaml.cs는 자동으로 L2XDBForm.xaml.cs로 이름이 변경 됩니다.

1. **L2xdbform.xaml** 파일에 있는 소스 코드를 [l2dbform.xaml 소스 코드로](l2dbform-xaml-source-code.md)바꿉니다. 이 파일 작업을 하려면 XAML 소스 뷰를 사용하세요.

1. 마찬가지로 **L2XDBForm.xaml.cs** 의 소스를 [L2DBForm.xaml.cs 원본 코드로](l2dbform-xaml-cs-source-code.md)바꿉니다.

1. 파일 **app.xaml**에서 **l2xdbform.xaml**를 사용 하 여 모든 문자열 **Window1** 을 바꿉니다.

1. **Ctrl**+**Shift**+**B**를 눌러 솔루션을 빌드합니다.

### <a name="run-the-app"></a>앱 실행

LinqToXmlDataBinding 앱을 사용 하면 포함 된 XML 요소로 저장 된 책 목록을 보고 조작할 수 있습니다. **F5** 키 (디버깅 시작) 또는 **Ctrl**+**F5** 키 (디버깅 하지 않고 시작)를 눌러 앱을 실행 합니다.

**LINQ to XML을 사용한 WPF 데이터 바인딩**이라는 제목의 프로그램 창이 나타납니다.

UI의 맨 위 섹션에는 책 목록을 나타내는 원시 **XML** 이 표시 됩니다. 이 섹션은 마우스나 키보드를 통해 조작할 수 없도록 하는 WPF <xref:System.Windows.Controls.TextBlock> 컨트롤을 사용하여 표시됩니다.

**Book List**라는 두 번째 세로 섹션에는 일반 텍스트로 정렬된 책 목록이 표시됩니다. 이 섹션에는 마우스나 키보드를 통해 선택할 수 있도록 하는 <xref:System.Windows.Controls.ListBox> 컨트롤이 사용됩니다.

### <a name="add-and-delete-books"></a>책 추가 및 삭제

새 책을 목록에 추가 하려면 마지막 섹션인 **새 책 추가**에서 **ID** 및 **값** <xref:System.Windows.Controls.TextBox> 컨트롤에 값을 입력 한 다음 **북 추가**를 선택 합니다. 책이 서적 및 XML 목록의 목록에 추가 됩니다. 이 프로그램에서는 입력 값의 유효성을 검사하지 않습니다.

목록에서 기존 책을 삭제 하려면 **Book list** 섹션에서 선택한 다음 **선택한 책 제거**를 선택 합니다. 책 항목은 책 및 원시 XML 원본 목록에서 제거 됩니다.

### <a name="edit-a-book-entry"></a>책 항목 편집

1. 두 번째 **Book List** 섹션에서 책 항목을 선택합니다.

   현재 값은 **선택한 책 편집** 섹션에 표시 됩니다.

1. 키보드를 사용하여 값을 편집합니다. <xref:System.Windows.Controls.TextBox> 제어가 포커스를 잃으면 즉시 변경 내용이 XML 원본 및 책 목록에 자동으로 전파 됩니다.
