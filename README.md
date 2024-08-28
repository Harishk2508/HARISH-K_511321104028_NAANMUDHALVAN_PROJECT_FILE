# HARISH-K_511321104028_NAANMUDHALVAN_PROJECT_FILE

FOR GITHUB README FILE:


PROJECT CREATED BY:

NAME: HARISH K

REGISTER NO: 511321104028

COLLEGE CODE: 5113

COLLEGE NAME:KINGSTON ENGINEERING COLLEGE

LOGIN DETAILS:

USERNAME: admin

PASSWORD: admin



@PostMapping("/book")
    public String bookRoom(@ModelAttribute Booking booking, RedirectAttributes redirectAttributes) {
        try {
            Booking savedBooking = userService.saveBooking(booking);
            redirectAttributes.addFlashAttribute("bookingId", savedBooking.getId());
            return "redirect:/booking-success";
        } catch (Exception e) {
            e.printStackTrace();
            redirectAttributes.addFlashAttribute("error", "An error occurred while processing your booking: " + e.getMessage());
            return "redirect:/booking-error";
        }
    }

    @GetMapping("/booking-success")
    public String showBookingSuccess(@ModelAttribute("bookingId") Long bookingId, Model model) {
        Booking booking = userService.getBookingById(bookingId);
        if (booking == null) {
            return "redirect:/booking-error";
        }
        model.addAttribute("booking", booking);
        return "success";
    }

    @GetMapping("/booking-error")
    public String showBookingError(@ModelAttribute("error") String error, Model model) {
        model.addAttribute("error", error);
        return "error";
    }
