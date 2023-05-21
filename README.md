:root {
  /** colors */
  --primary: #b5a1e5;
  --on-primary: #100e17;
  --background: #131214;
  --on-background: #eae6f2;
  --surface: #1d1c1f;
  --on-surface: #dddae5;
  --on-surface-variant: #7b7980;
  --on-surface-variant-2: #b9b6bf;
  --outline: #3e3d40;
  --bg-aqi-1: #89e589;
  --on-bg-aqi-1: #1f331f;
  --bg-aqi-2: #e5dd89;
  --on-bg-aqi-2: #33311f;
  --bg-aqi-3: #e5c089;
  --on-bg-aqi-3: #332b1f;
  --bg-aqi-4: #e58989;
  --on-bg-aqi-4: #331f1f;
  --bg-aqi-5: #e589b7;
  --on-bg-aqi-5: #331f29;
  --white: hsl(0, 0%, 100%);
  --white-alpha-4: hsla(0, 0%, 100%, 0.04);
  --white-alpha-8: hsla(0, 0%, 100%, 0.08);
  --black-alpha-10: hsla(0, 0%, 0%, 0.1);

  /*gradient colors */
  --gradient-1: linear-gradient(
    180deg,
    hsla(270, 5%, 7%, 0) 0%,
    hsla(270, 5%, 7%, 0.8) 65%,
    hsl(270, 5%, 7%) 100%
  );
  --gradient-2: linear-gradient(
    180deg,
    hsla(260, 5%, 12%, 0) 0%,
    hsla(260, 5%, 12%, 0.8) 65%,
    hsl(260, 5%, 12%) 100%
  );
  /*typography*/

  /*font family ***
  ***/
  --ff-nunito-sans: "Nunito Sans", sans-serif;
  /*font size */

  --heading: 5.6rem;
  --title-1: 2rem;
  --title-2: 1.8rem;
  --title-3: 1.6rem;
  --body-1: 2.2rem;
  --body-2: 2rem;
  --body-3: 1.6rem;
  --label-1: 1.4rem;
  --label-2: 1.2rem;

  /*font weight*/
  --weight-regular: 400;
  --weight-semiBold: 600;

  /*box shadow*/
  --shadow-1: 0px 1px 3px hsla(0, 0%, 0%, 0.5);
  --shadow-2: 0px 3px 6px hsla(0, 0%, 0%, 0.4);

  /**
  *border radius
  */
  --radius-28: 28px;
  --radius-16: 16px;
  --radius-pill: 500px;
  --radius-circle: 50%;

  /**
  *transition
  */
  --transition-short: 100ms ease;
}

/*-----------------------------------*\
  #RESET
\*-----------------------------------*/
*,
*::before,
*::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

li {
  list-style: none;
}

a,
img,
span,
input,
button {
  display: block;
}

a {
  color: inherit;
  text-decoration: none;
}
img {
  height: auto;
}

input,
button {
  background: none;
  border: none;
  color: inherit;
  font: inherit;
}
input {
  width: 100%;
}
button {
  cursor: pointer;
}

sub {
  vertical-align: baseline;
}
sup {
  vertical-align: top;
}
sub,
sup {
  font-size: 0.75em;
}
html {
  font-family: var(--ff-nunito-sans);
  font-size: 10px;
  scroll-behavior: smooth;
}
body {
  background-color: var(--background);
  color: var(--on-background);
  font-size: var(--body-3);
  overflow: hidden;
}
:focus-visible {
  outline: 2px solid var(--white);
  outline-offset: 2px;
}
::selection {
  background-color: var(--white-alpha-8);
}

::-webkit-scrollbar {
  width: 6px;
  height: 6px; /* for horizontal scrollbar*/
}
::-webkit-scrollbar-thumb {
  background-color: var(--white-alpha-8);
  border-radius: var(--radius-pill);
}
/*-----------------------------------*\
  #MATERIAL ICON
\*-----------------------------------*/
@font-face {
  font-family: "Material Symbols Rounded";
  font-style: normal;
  font-weight: 400;
  src: url(../font/material-symbol-rounded.woff2) format("woff2");
}
.m-icon {
  font-family: "Material Symbols Rounded";
  font-weight: normal;
  font-style: normal;
  font-size: 2.4rem;
  line-height: 1;
  letter-spacing: normal;
  text-transform: none;
  white-space: nowrap;
  word-wrap: normal;
  direction: ltr;
  font-feature-settings: "liga";
  -webkit-font-feature-settings: "liga";
  -webkit-font-smoothing: antialiased;
  height: 1em;
  width: 1em;
  overflow: hidden;
}

/*-----------------------------------*\
  #REUSED STYLE
\*-----------------------------------*/
.container {
  max-width: 1600px;
  width: 100%;
  margin-inline: auto;
  padding: 16px;
}
.icon-btn {
  background-color: var(--white-alpha-8);
  width: 48px;
  height: 48px;
  display: grid;
  place-items: center;
  border-radius: var(--radius-circle);
}
.has-state {
  position: relative;
}
.has-state:hover {
  box-shadow: var(--shadow-1);
}
.has-state:is(:focus, :focus-visible) {
  box-shadow: none;
}
.has-state::before {
  content: "";
  position: absolute;
  inset: 0;
  border-radius: inherit;
  clip-path: circle(100% at 50% 50%);
  transition: var(--transition-short);
}
.has-state:hover::before {
  background-color: var(--white-alpha-4);
}
.has-state:is(:focus, :focus-visible)::before {
  background-color: var(--white-alpha-8);
  animation: ripple 250ms ease forwards;
}
@keyframes ripple {
  0% {
    clip-path: circle(0% at 50% 50%);
  }
  100% {
    clip-path: circle(100% at 50% 50%);
  }
}
.btn-primary {
  background-color: var(--primary);
  color: var(--on-primary);
  height: 48px;
  line-height: 48px;
  max-width: max-content;
  display: flex;
  align-items: center;
  gap: 16px;
  padding-inline: 16px;
  border-radius: var(--radius-pill);
}
.btn-primary .span {
  font-weight: var(--weight-semiBold);
}

.btn-primary[disabled] {
  background-color: var(--outline);
  color: var(--on-surface-variant);
  cursor: not-allowed;
}
.btn-primary[disabled]::before {
  display: none;
}
.card {
  background-color: var(--surface);
  color: var(--on-surface);
}
.card-lg {
  border-radius: var(--radius-28);
  padding: 20px;
}
.card-sm {
  border-radius: var(--radius-16);
  padding: 16px;
}
.heading {
  color: var(--white);
  font-size: var(--heading);
  line-height: 1.1;
}
.title-1 {
  font-size: var(--title-1);
}

.title-2 {
  font-size: var(--title-2);
  margin-block-end: 12px;
}
.title-3 {
  font-size: var(--title-3);
  font-weight: var(--weight-semiBold);
}

.body-1 {
  font-size: var(--body-1);
}
.body-2 {
  font-size: var(--body-2);
  font-weight: var(--weight-semiBold);
}
.body-3 {
  font-size: var(--body-3);
}
.label-1 {
  font-size: var(--label-1);
}
.label-2 {
  font-size: var(--label-2);
}

/*-----------------------------------*\
  #HEADER
\*-----------------------------------*/
.header .btn-primary .span {
  display: none;
}
.logo img {
  width: 150px;
}
.header .container .header-actions {
  display: flex;
  align-items: center;
}
.header .container {
  justify-content: space-between;
}
.header-actions {
  gap: 16px;
}
.header .btn-primary {
  padding-inline: 12px;
}
.search-view {
  position: fixed;
  top: 100;
  left: 500;
  width: 100%;
  height: 100vh;
  height: 100svh;
  background-color: var(--surface);
  color: var(--on-surface);
  clip-path: circle(4% at calc(100% - 102px) 5%);
  opacity: 0;
  visibility: hidden;
  z-index: 4;
  transition: clip-path 500ms ease;
}
.search-view.active {
  opacity: 1;
  visibility: visible;
  clip-path: circle(130% at 73% 5%);
}
.search-wrapper {
  display: flex;
  justify-content: center;
  position: relative;
  border-block-end: 1px solid var(--outline);
}
.search-wrapper::before {
  content: "";
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  right: 16px;
  width: 24px;
  height: 24px;
  border: 3px solid var(--on-surface);
  border-block-start-color: transparent;
  border-radius: var(--radius-circle);
  animation: loading 500ms linear infinite;
  /* display: none; */
}
@keyframes loading {
  0% {
    transform: translateY(-50%) rotate(0);
  }
  100% {
    transform: translateY(-50%) rotate(1turn);
  }
}

.search-wrapper:has(.searching)::before {
  display: block;
}

.search-field {
  height: 80px;
  line-height: 80px;
  padding-inline: 56px 16px;
  outline: none;
}
.search-field::placeholder {
  color: var(--on-surface-variant-2);
}
.search-field::-webkit-search-cancel-button {
  display: none;
}
.search-wrapper.leading-icon {
  position: absolute;
  top: 50%;
  left: 28px;
  transform: translate(-50%, -50%);
}
.search-wrapper > .m-icon {
  display: none;
}
.search-wrapper .icon-btn {
  background-color: transparent;
  box-shadow: none;
}
.search-view .view-list {
  padding-block: 8px 16px;
}
.search-view .view-item {
  position: relative;
  height: 56px;
  display: flex;
  justify-content: flex-start;
  align-items: center;
  gap: 16px;
  padding-inline: 16px 24px;
}
.search-view .view-item :is(.micon, .item-subtitle) {
  color: var(--on-surface-variant);
}
.search-view .view-item .item-link {
  position: absolute;
  inset: 0;
  box-shadow: none;
}
/*-----------------------------------*\
  #MAIN
\*-----------------------------------*/
main {
  height: calc(100vh-80px);
  height: calc(100svh-80px);
  overflow: hidden;
}
article.container {
  position: relative;
  display: grid;
  grid-template-columns: minmax(0, 1fr);
  gap: 20px;
  overflow-y: auto; /*for firefox*/
  overflow-y: overlay;
}
article.container::-webkit-scrollbar-thumb {
  background-color: transparent;
}
article.container:is(:hover, :focus-within)::-webkit-scrollbar-thumb {
  background-color: var(--white-alpha-8);
}
article.container::-webkit-scrollbar-button {
  height: 10px;
}
article.container::before {
  content: "";
  position: fixed;
  bottom: 0;
  width: 100%;
  height: 40px;
  background-image: var(--gradient-1);
  pointer-events: none;
  z-index: 1;
}
.section:not(:last-child) {
  margin-block-end: 16px;
}
/*-----------------------------------*\
  Current WEATHER
\*-----------------------------------*/
.current-weather-card .wrapper {
  margin-block: 12px;
  display: flex;
  gap: 8px;
  align-items: center;
}
.current-weather-card .weather-icon {
  margin-inline: auto;
}
.current-weather-card > .body-3 {
  text-transform: capitalize;
}

.current-weather-card .meta-list {
  margin-block-start: 16px;
  padding-block-start: 16px;
  border-block-start: 1px solid var(--outline);
}
.current-weather-card .meta-item {
  display: flex;
  align-items: center;
  gap: 8px;
}
.current-weather-card .meta-item:not(:last-child) {
  margin-block-end: 12px;
}
.current-weather-card .meta-text {
  color: var(--on-surface-variant);
}

/*-----------------------------------*\
  #HIGHLIGHTS
\*-----------------------------------*/

.forecast-card .title-2 {
  margin-block-end: 0;
}
.forecast-card :is(.card-item, .icon-wrapper) {
  display: flex;
  align-items: center;
}
.forecast-card .card-item:not(:last-child) {
  margin-block-end: 12px;
}
.forecast-card .icon-wrapper {
  gap: 8px;
}
.forecast-card .label-1 {
  color: var(--on-surface-variant);
  font-weight: var(--weight-semiBold);
}
.forecast-card .card-item > .label-1 {
  width: 100%;
  text-align: right;
}

