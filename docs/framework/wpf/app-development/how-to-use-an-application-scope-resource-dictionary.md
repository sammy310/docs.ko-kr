---
title: '방법: 애플리케이션 범위 리소스 사전 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dictionaries [WPF], resource
- resource dictionaries [WPF], application-scope
- application-scope resource dictionaries
ms.assetid: 53857682-bd2c-4f2c-8f25-1307d0b451a2
ms.openlocfilehash: 5bfb3ed0304598a5acf4b7682bf4a4169c5153d1
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459802"
---
# <a name="how-to-use-an-application-scope-resource-dictionary"></a>방법: 애플리케이션 범위 리소스 사전 사용
이 예제에서는 애플리케이션 범위 사용자 지정 리소스 사전을 정의하고 사용하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 <xref:System.Windows.Application> <xref:System.Windows.Application.Resources%2A>공유 리소스에 대 한 응용 프로그램 범위 저장소를 노출 합니다. 기본적으로 <xref:System.Windows.Application.Resources%2A> 속성은 <xref:System.Windows.ResourceDictionary> 형식의 인스턴스를 사용 하 여 초기화 됩니다. <xref:System.Windows.Application.Resources%2A>를 사용 하 여 응용 프로그램 범위 속성을 가져오고 설정할 때이 인스턴스를 사용 합니다. 자세한 내용은 [방법: 응용 프로그램 범위 리소스 가져오기 및 설정](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348547(v=vs.100))을 참조 하세요.
  
 <xref:System.Windows.Application.Resources%2A>사용 하 여 설정 하는 리소스가 여러 개 있는 경우에는 대신 사용자 지정 리소스 사전을 사용 하 여 해당 리소스를 저장 하 고 대신 <xref:System.Windows.Application.Resources%2A>를 설정할 수 있습니다. 다음에서는 XAML을 사용 하 여 사용자 지정 리소스 사전을 선언 하는 방법을 보여 줍니다.
  
 [!code-xaml[HOWTOResourceDictionaries#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MyResourceDictionary.xaml#1)]  
  
 <xref:System.Windows.Application.Resources%2A>를 사용 하 여 전체 리소스 사전을 바꾸면 각 테마가 단일 리소스 사전에 캡슐화 되는 응용 프로그램 범위 테마를 지원할 수 있습니다. 다음 예에서는 <xref:System.Windows.ResourceDictionary>를 설정 하는 방법을 보여 줍니다.  
  
 [!code-xaml[HOWTOResourceDictionaries#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/App.xaml#2)]  
  
 다음은 XAML의 <xref:System.Windows.Application.Resources%2A>에 의해 노출 되는 리소스 사전에서 응용 프로그램 범위 리소스를 가져오는 방법을 보여 줍니다.  
  
 [!code-xaml[HOWTOResourceDictionaries#4](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml#4)]  
  
 다음 예제에서는 코드에서 리소스를 가져오는 방법을 보여 줍니다.  
  
 [!code-csharp[HOWTOResourceDictionaries#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml.cs#3)]
 [!code-vb[HOWTOResourceDictionaries#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToResourceDictionaries/VB/MainWindow.xaml.vb#3)]  
  
 <xref:System.Windows.Application.Resources%2A>를 사용할 때 고려해 야 할 두 가지 사항이 있습니다. 먼저 사전 *키* 가 개체 이므로 속성 값을 설정 하 고 가져올 때 정확히 동일한 개체 인스턴스를 사용 해야 합니다. 문자열을 사용 하는 경우 키가 대/소문자를 구분 합니다. 둘째, 사전 *값* 은 개체 이므로 속성 값을 가져올 때 값을 원하는 형식으로 변환 해야 합니다.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.ResourceDictionary>
- <xref:System.Windows.Application.Resources%2A>
- [XAML 리소스](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [병합된 리소스 사전](../advanced/merged-resource-dictionaries.md)
