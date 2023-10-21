# fullcalendar
일반 캘린더가 아닌 full화면을 채우는 캘린더 입니다.

# 라이브러리 설치 
npm install @fullcalendar/react @fullcalendar/daygrid
 
# 핵심 코드 
```
import React from 'react';
import FullCalendar from '@fullcalendar/react';
import dayGridPlugin from '@fullcalendar/daygrid';

const Calendar = () => {
  return (
    <div className="calendar-container">
      <FullCalendar
        plugins={[dayGridPlugin]}
        initialView="dayGridMonth" // Set the initial view
        events={[
          // Provide an array of events here
          {
            title: 'Meeting with Client',
            date: '2023-10-21',
          },
          {
            title: 'Team Standup',
            date: '2023-10-25',
          },
          // Add more events as needed
        ]}
      />
    </div>
  );
};

export default Calendar;
```