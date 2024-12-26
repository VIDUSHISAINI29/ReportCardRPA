<script setup>
import { ref, watch } from "vue";

const sidebarDisplay = ref('tw-flex');
const categoryReport = ref(['Excellent', 'Good', 'Satisfatory', 'Need Improvement', 'Poor']);
// #1  JS (Functions & Variables) of Attendence Part of Report

const attPlaceholder = ref("Select Attendence Record");
const selectedAttReport = ref("Selected Attendence Report ");
const showAttOptions = ref(false);
const attReportBg = ref('');
const attReport = ref([
   {
      name: "The student has maintained near-perfect attendance, consistently showing a strong commitment to their education. They rarely miss class and are always punctual, demonstrating a high level of responsibility. This dedication greatly contributes to their academic success and engagement with the lessons.",
      code: "Excellent",
      bgColor: "tw-bg-green-200 hover:tw-bg-green-400",
      bgColorCard: "tw-bg-green-400",
   },
   {
      name: "The student attends school regularly with only a few absences, indicating a responsible attitude toward their education. They manage their time well and prioritize school commitments. While occasional absences occur, they ensure minimal disruption to their learning progress.",
      code: "Good",
      bgColor: "tw-bg-blue-200 hover:tw-bg-blue-400",
      bgColorCard: "tw-bg-blue-400",
   },
   {
      name: "The student’s attendance is satisfactory, but occasional absences suggest a need for better consistency. While they attend most classes, these absences sometimes affect their ability to fully engage with the material. A more consistent attendance pattern could help improve their academic performance.",
      code: "Satisfactory",
      bgColor: "tw-bg-yellow-200 hover:tw-bg-yellow-400",
      bgColorCard: "tw-bg-yellow-400",
   },
   {
      name: "Frequent absences have slightly impacted the student’s learning progress and understanding of key concepts. While they attend most classes, they miss crucial lessons that affect their performance. Regular attendance would greatly benefit their overall academic achievement.",
      code: "Need Improvement",
      bgColor: "tw-bg-orange-200 hover:tw-bg-orange-400",
      bgColorCard: "tw-bg-'orange'-400",
   },
   {
      name: "Irregular attendance has significantly hindered the student’s ability to stay updated with classroom activities and lessons. Their frequent absences make it difficult for them to keep up with coursework. It is crucial for the student to improve attendance to ensure continued academic progress.",
      code: "Poor",
      bgColor: "tw-bg-red-200 hover:tw-bg-red-400",
      bgColorCard: "tw-bg-red-400",
   },
]);

function triggerAttDropdown(params) {
   const modifyValue = params.name.slice(0, 30) + "...";
   attPlaceholder.value = modifyValue;
   selectedAttReport.value = params.name;
   attReportBg.value = params.bgColorCard
   showAttOptions.value = false;
}
function triggerAttDropdownTrue() {
   showAttOptions.value = !showAttOptions.value;
   showAcademicOptions.value =
      showExCurOptions.value =
      showOverallOptions.value =
         false;
}

// #2  JS (Functions & Variables) of Academic Part of Report

const academicPlaceholder = ref("Select Academic Record");
const selectedAcademicReport = ref("Selected Academic Report");
const showAcademicOptions = ref(false);
const academicReportBg = ref('');
const academicReport = ref([
   {
      name: "The student demonstrates exceptional academic skills, consistently exceeding expectations across all subjects. They actively engage in class discussions, complete assignments with precision, and showcase a thorough understanding of complex concepts. Their ability to think critically and solve problems creatively sets them apart.",
      code: "Excellent",
      bgColor: "tw-bg-green-200 hover:tw-bg-green-400",
      bgColorCard: "tw-bg-green-400",
   },
   {
      name: "The student has a strong academic foundation and performs well in most areas. They actively participate in class and complete assignments on time. Occasionally, they may need support with more advanced topics, but their overall performance reflects dedication and hard work.",
      code: "Good",
      bgColor: "tw-bg-blue-200 hover:tw-bg-blue-400",
      bgColorCard: "tw-bg-blue-400",
   },
   {
      name: "The student has a satisfactory understanding of the core subjects. While they perform well in familiar topics, they sometimes face challenges in new or complex areas. With consistent effort and additional practice, they have the potential to enhance their skills and performance.",
      code: "Satisfactory",
      bgColor: "tw-bg-yellow-200 hover:tw-bg-yellow-400",
      bgColorCard: "tw-bg-yellow-400",
   },
   {
      name: "The student struggles with certain subjects and requires focused guidance to improve their academic performance. They may lack confidence in applying concepts and need encouragement to actively participate in class. Regular practice and personalized attention could help them overcome these challenges.",
      code: "Needs Improvement",
      bgColor: "tw-bg-orange-200 hover:tw-bg-orange-400",
      bgColorCard: "tw-bg-orange-400",
   },
   {
      name: "The student's academic performance is significantly below expectations. They face difficulty understanding fundamental concepts and often need substantial support to complete tasks. A structured intervention plan, combined with consistent encouragement, is essential to help them progress.",
      code: "Poor",
      bgColor: "tw-bg-red-200 hover:tw-bg-red-400",
      bgColorCard: "tw-bg-red-400",
   },
]);

function triggerAcademicDropdown2(params) {
   const modifyValue = params.name.slice(0, 30) + "...";
   academicPlaceholder.value = modifyValue;
   selectedAcademicReport.value = params.name;
   academicReportBg.value = params.bgColorCard
   showAcademicOptions.value = false;
}
function triggerAcademicDropdownTrue2() {
   showAcademicOptions.value = !showAcademicOptions.value;
   showAttOptions.value =
      showExCurOptions.value =
      showOverallOptions.value =
         false;
}

// #3  JS (Functions & Variables) of C-Curricular Part of Report

const exCurPlaceholder = ref("Select Co-curricular Record");
const selectedExCurReport = ref("Selected Co-curricular Report");
const showExCurOptions = ref(false);
const exCurReportBg = ref('');
const exCurricularsReport = ref([
   {
      name: "The student demonstrates exceptional involvement in extracurricular activities, consistently exceeding expectations. They show strong leadership skills, contribute effectively to group tasks, and take initiative in organizing events. Their creativity and passion for extracurriculars inspire others and set a high standard for their peers.",
      code: "Excellent",
      bgColor: "tw-bg-green-200 hover:tw-bg-green-400",
      bgColorCard: "tw-bg-green-400",
   },
   {
      name: "The student is highly engaged in extracurricular activities and consistently performs well. They contribute meaningfully to group projects, exhibit a positive attitude, and actively participate in events. While they occasionally need support with larger or more complex activities, their overall involvement is impressive.",
      code: "Good",
      bgColor: "tw-bg-blue-200 hover:tw-bg-blue-400",
      bgColorCard: "tw-bg-blue-400",
   },
   {
      name: "The student participates in extracurricular activities with a solid level of engagement. They contribute positively to group tasks and attend most events. However, they sometimes struggle with new or unfamiliar activities, requiring additional effort and practice to fully excel in these areas.",
      code: "Satisfactory",
      bgColor: "tw-bg-yellow-200 hover:tw-bg-yellow-400",
      bgColorCard: "tw-bg-yellow-400",
   },
   {
      name: "The student shows limited involvement in extracurricular activities and faces challenges in contributing effectively. They often lack confidence in leadership roles and may find it difficult to work in group settings. With focused guidance and encouragement, they have the potential to improve their participation.",
      code: "Needs Improvement",
      bgColor: "tw-bg-orange-200 hover:tw-bg-orange-400",
      bgColorCard: "tw-bg-orange-400",
   },
   {
      name: "The student struggles significantly with extracurricular activities and rarely engages in events. They have difficulty taking on tasks or contributing to group efforts and often require substantial support. A more structured plan, along with consistent motivation and encouragement, is necessary to help them become more involved.",
      code: "Poor",
      bgColor: "tw-bg-red-200 hover:tw-bg-red-400",
      bgColorCard: "tw-bg-red-400",
   },
]);

function triggerExCurDropdown2(params) {
   const modifyValue = params.name.slice(0, 30) + "...";
   exCurPlaceholder.value = modifyValue;
   selectedExCurReport.value = params.name;
   exCurReportBg.value = params.bgColorCard
   showExCurOptions.value = false;
}
function triggerExCurDropdownTrue2() {
   showExCurOptions.value = !showExCurOptions.value;
   showAttOptions.value =
      showAcademicOptions.value =
      showOverallOptions.value =
         false;
}

// #3  JS (Functions & Variables) of Overall Performance Part of Report

const overallReport = ref([
   {
      name: "The student consistently excels in all subjects, demonstrating outstanding academic performance. They actively participate in class discussions, complete assignments with great detail, and show a high level of intellectual curiosity. Their work is consistently of the highest quality, and they often go above and beyond expectations. This student is a role model for peers and a strong contributor to the school community.",
      code: "Excellent",
      bgColor: "tw-bg-green-200 hover:tw-bg-green-400",
      bgColorCard: "tw-bg-green-400",
   },
   {
      name: "The student performs well in most subjects, maintaining a strong grasp of the material. They are diligent and consistently submit assignments on time, although there is some room for improvement in certain areas. Overall, they demonstrate a positive attitude toward learning and contribute meaningfully in class. With continued effort, they have the potential to achieve even greater success.",
      code: "Good",
      bgColor: "tw-bg-blue-200 hover:tw-bg-blue-400",
      bgColorCard: "tw-bg-blue-400",
   },
   {
      name: "The student’s performance is generally satisfactory, though there are some areas that need attention. While they complete most assignments and participate in class, they may occasionally struggle with certain concepts or exhibit inconsistency in their work. Focusing on areas of weakness and maintaining a more consistent effort could help improve their overall academic performance.",
      code: "Satisfactory",
      bgColor: "tw-bg-yellow-200 hover:tw-bg-yellow-400",
      bgColorCard: "tw-bg-yellow-400",
   },
   {
      name: "The student’s academic performance requires improvement. While they show some understanding of the material, there are frequent gaps in their knowledge and understanding of key concepts. This is often due to inconsistent effort or lack of engagement in class activities. With more focus, participation, and effort, their performance can improve significantly.",
      code: "Need Improvement",
      bgColor: "tw-bg-orange-200 hover:tw-bg-orange-400",
      bgColorCard: "tw-bg-orange-400",
   },
   {
      name: "The student is struggling academically, with frequent challenges in understanding the material and completing assignments. Their performance is below expectations, often due to lack of consistent effort, participation, and focus. It is essential for the student to seek additional support and adopt a more proactive approach to learning in order to make progress and improve their grades.",
      code: "Poor",
      bgColor: "tw-bg-red-200 hover:tw-bg-red-400",
      bgColorCard: "tw-bg-red-400",
   },
]);
const overallPlaceholder = ref("Select Overall Performance Record");
const selectedOverallReport = ref("Selected Overall Performance Report");
const overallReportBg = ref('');
const showOverallOptions = ref(false);

function triggerOverallDropdown2(params) {
   const modifyValue = params.name.slice(0, 30) + "...";
   overallPlaceholder.value = modifyValue;
   selectedOverallReport.value = params.name;
   overallReportBg.value = params.bgColorCard
   console.log('overall', overallReportBg.value);
   
   showOverallOptions.value = false;
}
function triggerOverallDropdownTrue2() {
   showOverallOptions.value = !showOverallOptions.value;
   showAttOptions.value =
      showAcademicOptions.value =
      showExCurOptions.value =
         false;
}



  function downloadPdf() {
   const { jsPDF } = window.jspdf;
        const doc = new jsPDF({
            orientation: 'portrait', // Set orientation ('portrait' or 'landscape')
            unit: 'px',              // Use pixels as the unit
            format: 'a4',            // Set page size to A4
        });

        const content = document.getElementById('rendered-content');

        const contentWidth = content.offsetWidth;  // Width of your HTML content
        const contentHeight = content.offsetHeight;

        console.log('width : ', contentWidth);
        console.log('hwight : ', contentHeight);
        

        doc.html(content, {
            callback: function (doc) {
                // Save the PDF
                doc.save('Report-Card.pdf');
            },
            x: 0,          // Margin from left
            y: -6,          // Margin from top
            autoPaging: false, // Ensures everything is on a single page
            html2canvas: {
            scale: 0.5,    // Adjust to fit content
            scrollX: 0,    // Prevent shifting
            scrollY: 0,
            useCORS: true  // Fix external resources rendering
        }
        });
    };


</script>

<template>
   <div class="tw-flex tw-w-full tw-justify-center tw-select-none">
      <div id="rendered-content" class="tw-w-[893px] tw-h-[1263px] tw-flex tw-justify-center tw-items-center tw-p-1 tw-bg-[#f8f4e3] tw-border-[#61b132] tw-border-[4px]">
         <div 
         class=" tw-flex tw-w-[885px] tw-h-[1249px] tw-border-[#61b132] tw-border-2 tw-flex-col tw-items-center tw-gap-12  tw-bg-[#f8f4e3] ">
         <span class="tw-text-4xl tw-font-bold tw-mt-8 tw-text-[#61b132]">
            Report Card
         </span>
         <div class="tw-flex tw-w-4/5 tw-flex-col tw-gap-3">
            <div class="tw-flex tw-flex-col tw-w-full tw-gap-6 tw-p-1">
               <div
                  class="tw-w-full tw-border-b-[2px]   tw-flex tw-border-[#b8a975] tw-px-1 tw-text-sm tw-font-semibold">
                  <span>Student :</span> 
                  <input type="text" name="" id="" placeholder="Enter Name " class="tw-border-none tw-px-4 tw-text[#b8a975] tw-outline-none tw-bg-[#f8f4e3]">
               </div>
               <div
                  class="tw-w-full tw-border-b-[2px]    tw-border-[#b8a975] tw-px-1 tw-text-sm tw-font-semibold">
                  <span>Class :</span>
                  <input type="text" name="" id="" placeholder="Enter Class " class="tw-border-none tw-px-4 tw-text[#b8a975] tw-outline-none tw-bg-[#f8f4e3]">
               </div>
               <div
                  class="tw-w-full tw-border-b-[2px]   tw-border-[#b8a975] tw-px-1 tw-text-sm tw-font-semibold">
                  <span>Father's Name :</span>
                  <input type="text" name="" id="" placeholder="Enter Father's Name " class="tw-border-none tw-px-4 tw-text[#b8a975] tw-outline-none tw-bg-[#f8f4e3]">
               </div>
               <div
                  class="tw-w-full tw-border-b-[2px]   tw-border-[#b8a975] tw-px-1 tw-text-sm tw-font-semibold">
                  <span>Class Incharge :</span>
                  <input type="text" name="" id="" placeholder="Enter Class Teacher Name " class="tw-border-none tw-px-4 tw-text[#b8a975] tw-outline-none tw-bg-[#f8f4e3]">
               </div>
               <div
                  class="tw-w-full tw-border-b-[2px]  tw-border-[#b8a975] tw-px-1 tw-text-sm tw-font-semibold">
                  <span>Percentage :</span>
                  <input type="text" name="" id="" placeholder="Enter Percentage Scored " class="tw-border-none tw-px-4 tw-text[#b8a975] tw-outline-none tw-bg-[#f8f4e3]">
               </div>
            </div>
            <!-- <div class="tw-flex tw-w-full tw-justify-between tw-p-1">
               
            </div> -->
            <!-- <div class="tw-flex tw-w-full tw-justify-between tw-p-1">
              
               <div
                  class="tw-w-[45%] tw-border-b-4 tw-p-1  tw-border-[#b8a975] tw-px-1 tw-text-sm tw-font-semibold">
                  <span>Categorized As :</span>
                  <input type="text" name="" id="" placeholder="Enter Category " class="tw-border-none tw-px-4 tw-text[#b8a975] tw-outline-none tw-bg-[#f8f4e3]">
               </div>
            </div> -->
         </div>
         <div class="tw-flex tw-w-4/5 tw-flex-col tw-gap-3">
            <div class="tw-w-full tw-p-1 tw-bg-white tw-flex tw-rounded-md tw-px-3 tw-gap-10">
               <div v-for="(category, index) in categoryReport" class="tw-flex tw-items-center tw-gap-2">
                  <span :class="['tw-w-3 tw-h-3', overallReport[index].bgColorCard]"></span>
                  <span class="tw-font-bold tw-text-sm">{{category}}</span>
               </div>
            </div>
            <div
               class="tw-w-full tw-rounded-lg tw-bg-[#61b132] tw-p-1 tw-py-2 tw-text-center tw-text-lg tw-font-semibold tw-text-white">
               <span>Student's Report</span>
            </div>
            <div
               class="tw-flex tw-w-full tw-flex-col tw-gap-4 tw-border-4 tw-border-[#61b132] tw-bg-white tw-p-3">
               <span :class="['tw-block tw-font-semibold  tw-p-2 tw-rounded-lg tw-text-[12px]', attReportBg]">
                 <span class="tw-block tw-text-[12px] tw-font-bold">Attendence Report : </span>
                 {{ selectedAttReport }}
               </span>
               <span :class="['tw-block tw-font-semibold  tw-p-2 tw-rounded-lg tw-text-[12px]', academicReportBg]">
                  <span class="tw-block tw-text-[12px] tw-font-bold">Academic Report : </span>
                  {{ selectedAcademicReport }}
               </span>
               <span :class="['tw-block tw-font-semibold  tw-p-2 tw-rounded-lg tw-text-[12px]', exCurReportBg]">
                  <span class="tw-block tw-text-[12px] tw-font-bold">Co-curriculum Report : </span>
                  {{ selectedExCurReport }}
               </span>
               <span :class="['tw-block tw-font-semibold  tw-p-2 tw-rounded-lg tw-text-[12px]', overallReportBg]">
                  <span class="tw-block tw-text-[12px] tw-font-bold">Overall Performance Report : </span>
                  {{ selectedOverallReport }}
               </span>
            </div>
         </div>
        <div class="tw-w-4/5 tw-flex tw-flex-col tw-gap-4">
         <div class=" tw-w-full tw-p-1 tw-flex tw-justify-between"> 
            <div class="tw-w-[45%] tw-px-1 tw-p-1  tw-text-sm tw-font-semibold tw-border-[#b8a975] tw-border-b-4">
               <span>Class Incharge Sign. :</span>
            </div>
            <div class="tw-w-[45%] tw-px-1 tw-p-1  tw-text-sm tw-font-semibold tw-border-[#b8a975] tw-border-b-4">
               <span>Principal Sign. :</span>
            </div>
         </div>
         
        </div>
        <div @click="downloadPdf" class="tw-cursor-pointer tw-bg-[#8c7319] tw-p-2 tw-px-3 tw-rounded-md tw-text-white tw-text-sm" id="download-pdf"><span>Download Pdf</span></div>
      </div>
      </div>
      <div  :class="['tw-w-1/4  tw-items-center tw-flex-col tw-gap-4 tw-mt-20 tw-bg-white tw-p-2', sidebarDisplay]">
         <!-- #1  Select for Attendence Part of Report -->

         <div class="tw-relative tw-flex tw-w-72 tw-flex-col tw-p-1">
            <span class="tw-px-2 tw-py-1 tw-text-[13px] tw-font-bold">
               Select Attendence Report
            </span>
            <span
               @click="triggerAttDropdownTrue"
               class="tw-block tw-w-full tw-cursor-pointer tw-rounded-md tw-text-white tw-bg-[#8c7319] tw-p-2 tw-text-[15px] tw-shadow-lg">
               {{ attPlaceholder }}
            </span>
            <ul
               class="tw-absolute tw-z-10 tw-mt-[70px] tw-flex tw-w-[97%] tw-origin-top tw-transform tw-flex-col tw-gap-1 tw-rounded-lg tw-bg-white tw-p-1 tw-shadow-xl tw-transition-transform tw-duration-500 tw-ease-in-out"
               :class="showAttOptions ? 'tw-scale-y-100' : 'tw-scale-y-0'"
               style="transform-origin: top">
               <li
                  @click="triggerAttDropdown(behaviour)"
                  v-for="(behaviour, index) in attReport"
                  :key="index"
                  :class="[
                     'tw-w-full tw-cursor-pointer tw-rounded-lg tw-px-4 tw-py-2 tw-transition-colors tw-duration-200',
                     behaviour.bgColor,
                  ]">
                  {{ behaviour.name.slice(0, 50) + "..." }}
               </li>
            </ul>
         </div>

         <!-- #2  Select for Academic Part of Report -->

         <div class="tw-relative tw-flex tw-w-72 tw-flex-col tw-p-1">
            <span class="tw-px-2 tw-py-1 tw-text-[13px] tw-font-bold">
               Select Academic Report
            </span>
            <span
               @click="triggerAcademicDropdownTrue2"
               class="tw-block tw-w-full tw-cursor-pointer tw-rounded-md tw-text-white tw-bg-[#8c7319] tw-p-2 tw-text-[15px] tw-shadow-lg">
               {{ academicPlaceholder }}
            </span>
            <ul
               class="tw-absolute tw-z-10 tw-mt-[70px] tw-flex tw-w-[97%] tw-origin-top tw-transform tw-flex-col tw-gap-1 tw-rounded-lg tw-bg-white tw-p-1 tw-shadow-xl tw-transition-transform tw-duration-500 tw-ease-in-out"
               :class="showAcademicOptions ? 'tw-scale-y-100' : 'tw-scale-y-0'"
               style="transform-origin: top">
               <li
                  @click="triggerAcademicDropdown2(behaviour)"
                  v-for="(behaviour, index) in academicReport"
                  :key="index"
                  :class="[
                     'tw-w-full tw-cursor-pointer tw-rounded-lg tw-px-4 tw-py-2 tw-transition-colors tw-duration-200',
                     behaviour.bgColor,
                  ]">
                  {{ behaviour.name.slice(0, 50) + "..." }}
               </li>
            </ul>
         </div>

         <!-- #3 Select for Co-curricular Part of Report -->

         <div class="tw-relative tw-flex tw-w-72 tw-flex-col tw-p-1">
            <span class="tw-px-2 tw-py-1 tw-text-[13px] tw-font-bold">
               Select Co-curriculum Activities Report
            </span>
            <span
               @click="triggerExCurDropdownTrue2"
               class="tw-block tw-w-full tw-cursor-pointer tw-rounded-md tw-text-white tw-bg-[#8c7319] tw-p-2 tw-text-[15px] tw-shadow-lg">
               {{ exCurPlaceholder }}
            </span>
            <ul
               class="tw-absolute tw-z-10 tw-mt-[70px] tw-flex tw-w-[97%] tw-origin-top tw-transform tw-flex-col tw-gap-1 tw-rounded-lg tw-bg-white tw-p-1 tw-shadow-xl tw-transition-transform tw-duration-500 tw-ease-in-out"
               :class="showExCurOptions ? 'tw-scale-y-100' : 'tw-scale-y-0'"
               style="transform-origin: top">
               <li
                  @click="triggerExCurDropdown2(behaviour)"
                  v-for="(behaviour, index) in exCurricularsReport"
                  :key="index"
                  :class="[
                     'tw-w-full tw-cursor-pointer tw-rounded-lg tw-px-4 tw-py-2 tw-transition-colors tw-duration-200',
                     behaviour.bgColor,
                  ]">
                  {{ behaviour.name.slice(0, 50) + "..." }}
               </li>
            </ul>
         </div>

         <!-- #4 Select for overall Performance Part of Report -->

         <div class="tw-relative  tw-flex tw-w-72 tw-flex-col tw-p-1">
            <span class="tw-px-2 tw-py-1 tw-text-[13px] tw-font-bold">
               Select Overall Performance Report
            </span>
            <span
               @click="triggerOverallDropdownTrue2"
               class="tw-block tw-w-full tw-cursor-pointer tw-rounded-md tw-text-white tw-bg-[#8c7319] tw-p-2 tw-text-[15px] tw-shadow-lg">
               {{ overallPlaceholder }}
            </span>
            <ul
               class="tw-absolute tw-z-10 tw-mt-[70px] tw-flex tw-w-[97%] tw-origin-top tw-transform tw-flex-col tw-gap-1 tw-rounded-lg tw-bg-white tw-p-1 tw-shadow-xl tw-transition-transform tw-duration-500 tw-ease-in-out"
               :class="showOverallOptions ? 'tw-scale-y-100' : 'tw-scale-y-0'"
               style="transform-origin: top">
               <li
                  @click="triggerOverallDropdown2(behaviour)"
                  v-for="(behaviour, index) in overallReport"
                  :key="index"
                  :class="[
                     'tw-w-full tw-cursor-pointer tw-rounded-lg tw-px-4 tw-py-2 tw-transition-colors tw-duration-200',
                     behaviour.bgColor,
                  ]">
                  {{ behaviour.name.slice(0, 50) + "..." }}
               </li>
            </ul>
         </div>
         <span @click="sidebarDisplay = 'tw-hidden'" class="tw-p-1 tw-text-center tw-w-28 tw-text-white tw-bg-black tw-rounded-md tw-cursor-pointer">Hide_Section</span>
        
      </div>
   </div>
</template>
<style scoped>

</style>