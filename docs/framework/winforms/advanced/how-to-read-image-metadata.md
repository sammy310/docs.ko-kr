---
title: '방법: 이미지 메타데이터 읽기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- metadata [Windows Forms], property item
- metadata [Windows Forms], reading image
ms.assetid: 72ec0b31-0be7-444a-9575-1dbcb864e0be
ms.openlocfilehash: 0a53e9b9d23c03715bf3088a4ae8577a39527995
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59173617"
---
# <a name="how-to-read-image-metadata"></a>방법: 이미지 메타데이터 읽기
일부 이미지 파일 이미지의 기능을 확인 하려면 읽을 수 있는 메타 데이터를 포함 합니다. 예를 들어, 디지털 사진 제조업체 및 모델의 이미지 캡처에 사용한 카메라 결정할 읽을 수 있는 메타 데이터를 포함할 수 있습니다. 사용 하 여 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], 기존 메타 데이터를 읽을 수 있습니다 및 이미지 파일에 새 메타 데이터를 쓸 수도 있습니다.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 메타 데이터의 개별 항목을 저장 한 <xref:System.Drawing.Imaging.PropertyItem> 개체입니다. 읽을 수 있습니다는 <xref:System.Drawing.Image.PropertyItems%2A> 의 속성을 <xref:System.Drawing.Image> 파일에서 모든 메타 데이터를 검색할 개체입니다. 합니다 <xref:System.Drawing.Image.PropertyItems%2A> 속성의 배열을 반환 <xref:System.Drawing.Imaging.PropertyItem> 개체입니다.  
  
 A <xref:System.Drawing.Imaging.PropertyItem> 개체에는 다음 네 가지 속성이: `Id`를 `Value`를 `Len`, 및 `Type`합니다.  
  
## <a name="id"></a>ID  
 메타 데이터 항목을 식별 하는 태그입니다. 에 할당할 수 있는 일부 값 <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 다음 표에 나와 있습니다.  
  
|16 진수 값|설명|  
|-----------------------|-----------------|  
|0x0320<br /><br /> 0x010F<br /><br /> 0x0110<br /><br /> 0x9003<br /><br /> 0x829A<br /><br /> 0x5090<br /><br /> 0x5091|이미지 제목<br /><br /> 장비 제조업체<br /><br /> 장치 모델<br /><br /> ExifDTOriginal<br /><br /> Exif 노출 시간<br /><br /> 광도 테이블<br /><br /> 색차 테이블|  
  
## <a name="value"></a>값  
 배열 값입니다. 값 형식의 도달한는 <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 속성입니다.  
  
## <a name="len"></a>Len  
 가리키는 값의 배열 (메가바이트) 길이 <xref:System.Drawing.Imaging.PropertyItem.Value%2A> 속성입니다.  
  
## <a name="type"></a>형식  
 배열에 있는 값의 데이터 형식은 가리키는 `Value` 속성입니다. 형식으로 표시 된 `Type` 속성 값은 다음 표에 표시 됩니다  
  
|숫자 값|설명|  
|-------------------|-----------------|  
|1|`Byte`입니다.|  
|2|배열을 `Byte` ASCII로 인코딩된 개체|  
|3|16 비트 정수|  
|4|32 비트 정수|  
|5|두 배열의 `Byte` 분수를 나타내는 개체를|  
|6|사용되지 않음|  
|7|Undefined|  
|8|사용되지 않음|  
|10|`SLong`|  
|10|`SRational`|  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 다음 코드 예제를 읽고 파일의 일곱 가지 메타 데이터 표시 `FakePhoto.jpg`합니다. 두 번째 (인덱스 1) 속성 목록에 항목이 <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 는 0x010F (장비 제조업체) 및 <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (ASCII로 인코딩된 바이트 배열)입니다. 코드 예제에서는 해당 속성 항목의 값을 표시합니다.  
  
 코드에는 다음과 유사한 출력이 생성 됩니다.  
  
 `Property Item 0`  
  
 `id: 0x320`  
  
 `type: 2`  
  
 `length: 16 bytes`  
  
 `Property Item 1`  
  
 `id: 0x10f`  
  
 `type: 2`  
  
 `length: 17 bytes`  
  
 `Property Item 2`  
  
 `id: 0x110`  
  
 `type: 2`  
  
 `length: 7 bytes`  
  
 `Property Item 3`  
  
 `id: 0x9003`  
  
 `type: 2`  
  
 `length: 20 bytes`  
  
 `Property Item 4`  
  
 `id: 0x829a`  
  
 `type: 5`  
  
 `length: 8 bytes`  
  
 `Property Item 5`  
  
 `id: 0x5090`  
  
 `type: 3`  
  
 `length: 128 bytes`  
  
 `Property Item 6`  
  
 `id: 0x5091`  
  
 `type: 3`  
  
 `length: 128 bytes`  
  
 `The equipment make is Northwind Camera.`  
  
### <a name="code"></a>코드  
 [!code-csharp[System.Drawing.WorkingWithImages#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.WorkingWithImages#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다. 양식의 처리 <xref:System.Windows.Forms.Control.Paint> 이벤트 paint 이벤트 처리기에이 코드를 붙여넣습니다. 바꿔야 `FakePhoto.jpg` 는 이미지 이름 및 경로 시스템 및 가져오기에 사용할 수는 `System.Drawing.Imaging` 네임 스페이스입니다.  
  
## <a name="see-also"></a>참고자료

- [이미지, 비트맵 및 메타파일](images-bitmaps-and-metafiles.md)
- [이미지, 비트맵, 아이콘 및 메타파일 사용](working-with-images-bitmaps-icons-and-metafiles.md)
