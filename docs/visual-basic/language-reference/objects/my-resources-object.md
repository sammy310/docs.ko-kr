---
title: My.Resources 개체
ms.date: 07/20/2015
f1_keywords:
- My.Resources
- My.Resources.MyResources.ResourceManager
- My.Resources.MyResources.Culture
helpviewer_keywords:
- My.Resources object
ms.assetid: 34c3f2dc-7b87-432c-9d5f-17ea666bb266
ms.openlocfilehash: 7f5d81194123ad2151a494a3cb79aa1955e0fdad
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350335"
---
# <a name="myresources-object"></a>My.Resources 개체
응용 프로그램의 리소스에 액세스 하기 위한 속성 및 클래스를 제공 합니다.  
  
## <a name="remarks"></a>설명  
 `My.Resources` 개체는 응용 프로그램의 리소스에 대 한 액세스를 제공 하 고 응용 프로그램에 대 한 리소스를 동적으로 검색할 수 있도록 합니다. 자세한 내용은 [응용 프로그램 리소스 관리 (.net)](/visualstudio/ide/managing-application-resources-dotnet)를 참조 하세요.  
  
 `My.Resources` 개체는 전역 리소스만 노출 합니다. 폼과 연결 된 리소스 파일에 대 한 액세스 권한은 제공 하지 않습니다. 양식에서 양식 리소스에 액세스 해야 합니다.  
  
 `My.Resources` 개체에서 응용 프로그램의 문화권 관련 리소스 파일에 액세스할 수 있습니다. 기본적으로 `My.Resources` 개체는 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A> 속성의 문화권과 일치 하는 리소스 파일에서 리소스를 조회 합니다. 그러나이 동작을 재정의 하 고 리소스에 사용할 특정 문화권을 지정할 수 있습니다. 자세한 내용은 [데스크톱 앱의 리소스](../../../framework/resources/index.md)를 참조하세요.  
  
## <a name="properties"></a>속성  
 `My.Resources` 개체의 속성은 응용 프로그램의 리소스에 대 한 읽기 전용 액세스를 제공 합니다. 리소스를 추가 하거나 제거 하려면 **프로젝트 디자이너**를 사용 합니다. `My.Resources.`*context.resourcename*을 사용 하 여 **프로젝트 디자이너** 를 통해 추가 된 리소스에 액세스할 수 있습니다.  
  
 **솔루션 탐색기** 에서 프로젝트를 선택한 다음 **프로젝트** 메뉴에서 **새 항목 추가** 또는 **기존 항목 추가** 를 클릭 하 여 리소스 파일을 추가 하거나 제거할 수도 있습니다. `My.Resources.`*resourceFileName*`.`*context.resourcename*을 사용 하 여 이러한 방식으로 추가 된 리소스에 액세스할 수 있습니다.  
  
 각 리소스에는 이름, 범주 및 값이 있으며 이러한 리소스 설정에 따라 리소스에 액세스 하는 속성이 `My.Resources` 개체에 표시 되는 방식이 결정 됩니다. **프로젝트 디자이너**에 추가 된 리소스:  
  
- 이름은 속성의 이름을 결정 합니다.  
  
- 리소스 데이터는 속성의 값입니다.  
  
- 범주는 속성의 유형을 결정 합니다.  
  
|범주|속성 데이터 형식|  
|---|---|  
|**문자열**|[String](../../../visual-basic/language-reference/data-types/string-data-type.md)|  
|**이미지**|<xref:System.Drawing.Bitmap>|  
|**아이콘**|<xref:System.Drawing.Icon>|  
|**오디오**|<xref:System.IO.UnmanagedMemoryStream><br /><br /> <xref:System.IO.UnmanagedMemoryStream> 클래스는 <xref:System.IO.Stream> 클래스에서 파생 되므로 <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A> 메서드와 같이 스트림을 취하는 메서드와 함께 사용할 수 있습니다.|  
|**파일**|텍스트 파일에 대 한 -   [문자열](../../../visual-basic/language-reference/data-types/string-data-type.md) 입니다.<br />이미지 파일에 대 한 <xref:System.Drawing.Bitmap>를 -   합니다.<br />아이콘 파일에 대 한 <xref:System.Drawing.Icon>를 -   합니다.<br />사운드 파일에 대 한 <xref:System.IO.UnmanagedMemoryStream>를 -   합니다.|  
|**기타**|디자이너의 **유형** 열에 있는 정보에 따라 결정 됩니다.|  
  
## <a name="classes"></a>클래스  
 `My.Resources` 개체는 각 리소스 파일을 공유 속성이 있는 클래스로 노출 합니다. 클래스 이름은 리소스 파일의 이름과 같습니다. 이전 섹션에서 설명한 것 처럼 리소스 파일의 리소스는 클래스에서 속성으로 노출 됩니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 폼의 제목을 응용 프로그램 리소스 파일의 `Form1Title` 이라는 문자열 리소스로 설정 합니다. 예제가 작동 하려면 응용 프로그램의 리소스 파일에 `Form1Title` 라는 문자열이 있어야 합니다.  
  
 [!code-vb[VbVbalrMyResources#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#1)]  
  
## <a name="example"></a>예제  
 이 예제에서는 폼의 아이콘을 응용 프로그램의 리소스 파일에 저장 된 `Form1Icon` 라는 아이콘으로 설정 합니다. 예제가 작동 하려면 응용 프로그램의 리소스 파일에 `Form1Icon` 이라는 아이콘이 있어야 합니다.  
  
 [!code-vb[VbVbalrMyResources#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#2)]  
  
## <a name="example"></a>예제  
 이 예제에서는 폼의 배경 이미지를 응용 프로그램 리소스 파일에 있는 `Form1Background`이라는 이미지 리소스로 설정 합니다. 이 예제가 작동 하려면 응용 프로그램에 리소스 파일에 `Form1Background` 이라는 이미지 리소스가 있어야 합니다.  
  
 [!code-vb[VbVbalrMyResources#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#3)]  
  
## <a name="example"></a>예제  
 이 예제에서는 응용 프로그램의 리소스 파일에 `Form1Greeting` 이라는 오디오 리소스로 저장 된 소리를 재생 합니다. 예제가 작동 하려면 응용 프로그램에 리소스 파일에 `Form1Greeting` 이라는 오디오 리소스가 있어야 합니다. `My.Computer.Audio.Play` 메서드는 Windows Forms 응용 프로그램에만 사용할 수 있습니다.  
  
 [!code-vb[VbVbalrMyResources#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#4)]  
  
## <a name="example"></a>예제  
 이 예제에서는 응용 프로그램의 문자열 리소스에 대 한 프랑스어 문화권 버전을 검색 합니다. 리소스 이름은 `Message`입니다. `My.Resources` 개체에서 사용 하는 문화권을 변경 하기 위해이 예제에서는 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A>를 사용 합니다.  
  
 이 예제가 작동 하려면 응용 프로그램의 리소스 파일에 `Message` 라는 문자열이 있어야 하 고 응용 프로그램에는 해당 리소스 파일 Resources.fr의 프랑스어 문화권 버전이 있어야 합니다. 응용 프로그램에 프랑스어 문화권 버전의 리소스 파일이 없는 경우 `My.Resource` 개체는 기본 문화권 리소스 파일에서 리소스를 검색 합니다.  
  
 [!code-vb[VbVbalrMyResources#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#10)]  
  
## <a name="see-also"></a>참고자료

- [애플리케이션 리소스 관리(.NET)](/visualstudio/ide/managing-application-resources-dotnet)
- [데스크톱 앱의 리소스](../../../framework/resources/index.md)
