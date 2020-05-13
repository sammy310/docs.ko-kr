---
title: '방법: 지역화할 수 있는 애플리케이션에서 리소스 사용'
ms.date: 03/30/2017
helpviewer_keywords:
- applications [WPF], localizable
- localizable applications [WPF]
ms.assetid: 08539ad6-7fca-4f34-b82b-ff439e11dfa7
ms.openlocfilehash: 8f516a86036656b98add23d38c588b5c19be4d7a
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212477"
---
# <a name="how-to-use-resources-in-localizable-apps"></a>방법: 지역화할 수 있는 응용 프로그램에서 리소스 사용

지역화는 사용자 인터페이스를 다양 한 문화권에 맞게 조정 하는 것을 의미 합니다. 이렇게 하려면 제목, 캡션 및 목록 상자 항목과 같은 텍스트를 번역 해야 합니다. 번역을 더 쉽게 수행 하기 위해 번역할 항목이 리소스 파일로 수집 됩니다. 지역화를 위한 리소스 파일을 만드는 방법에 대 한 자세한 내용은 [응용 프로그램 지역화](how-to-localize-an-application.md) 를 참조 하세요. WPF 응용 프로그램을 지역화 가능 하 게 만들려면 개발자가 지역화 가능한 리소스를 모두 리소스 어셈블리에 빌드해야 합니다. 리소스 어셈블리는 다른 언어로 지역화 되며 코드 숨김이 리소스 관리 API를 사용 하 여 로드 합니다.

## <a name="example"></a>예제

WPF 응용 프로그램에 필요한 파일 중 하나는 프로젝트 파일 (proj)입니다. 애플리케이션에서 사용하는 모든 리소스는 프로젝트 파일에 포함되어야 합니다. 다음 XAML 예제에서는이를 보여 줍니다.

```xaml
<Resource Include="data\picture1.jpg"/>  
<EmbeddedResource Include="data\stringtable.en-US.restext"/>
```

응용 프로그램에서 리소스를 사용 하려면 사용 하려는 <xref:System.Resources.ResourceManager> 리소스를 인스턴스화하고 로드 합니다. 다음 c # 코드에서는이 작업을 수행 하는 방법을 보여 줍니다.

[!code-csharp[LocalizationResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]

## <a name="see-also"></a>참고 항목

- [앱 지역화](how-to-localize-an-application.md)
